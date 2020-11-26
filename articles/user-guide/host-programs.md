---
title: Způsoby spuštění Q# programu
description: Přehled různých způsobů spouštění Q# programů. Z příkazového řádku, Q# poznámkových bloků Jupyter a klasických hostitelských programů v Pythonu nebo v jazyce .NET.
author: gillenhaalb
ms.author: a-gibec
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2c5bdebc826bb85f6d7e0ade6232e15e29e8fb19
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231685"
---
# <a name="ways-to-run-a-no-locq-program"></a>Způsoby spuštění Q# programu

Jednou z největších silou pro vývojová prostředí pro životní prostředí je jeho flexibilita napříč platformami a vývojovým prostředím.
To ale také znamená, že noví Q# Uživatelé můžou při [instalaci v instalační příručce](xref:microsoft.quantum.install)najít nebo přesvědčit o mnoha možnostech.
Na této stránce vysvětlete, co se stane Q# , když se program spustí, a porovnejte různé způsoby, jak to uživatelé můžou udělat.

Primární rozdíl je, že Q# lze spustit:
- jako samostatná aplikace, kde Q# je jediný jazyk, který je součástí jediného jazyka a který program je vyvolán přímo. Do této kategorie ve skutečnosti patří dvě metody:
  - rozhraní příkazového řádku
  - Q# Jupyter poznámkové bloky
- s dalším *hostitelským programem*, který je napsán v Pythonu nebo v jazyce .NET (například C# nebo F #), který potom vyvolá program a může pokračovat ve zpracování vrácených výsledků.

Abychom těmto procesům a jejich rozdílům nejlépe pochopili, Uvažujme o jednoduchém Q# programu a porovnejte způsob, jakým je možné ho spustit.

## <a name="basic-no-locq-program"></a>Základní Q# program

Základní program pro vystavování se může skládat z přípravy qubit do stejné pozice stavů $ \ket {0} $ a $ \ket {1} $, měření a vrácení výsledku, který bude náhodně buď jedna z těchto dvou stavů, se stejnou pravděpodobností.
Tento proces je skutečně v jádru pro rychlý Start [generátoru náhodných čísel](xref:microsoft.quantum.quickstarts.qrng) .

V nástroji Q# by to bylo provedeno následujícím kódem:

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

Samotný kód však nelze spustit pomocí Q# .
V takovém případě musí sestavovat tělo [operace](xref:microsoft.quantum.qsharp.operationsandfunctions), která je pak spuštěna při volání---buď přímo, nebo jinou operací. Proto můžete napsat operaci následujícího formuláře:
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
Definovali jste operaci, `MeasureSuperposition` která nepřijímá žádné vstupy a vrací hodnotu typu [Result](xref:microsoft.quantum.qsharp.typesystem-index#available-types).

Kromě operací Q# umožňuje také zapouzdřit deterministické výpočty do funkcí. Kromě determinismem záruky, která implikuje, že se výpočty, které se chovají na qubits, musí zapouzdřit do operací místo funkcí, existuje malý rozdíl mezi operacemi a funkcemi. Odkázat na ně souhrnně jako *volatelné*.

### <a name="callable-defined-in-a-no-locq-file"></a>V souboru se nedá volat definice. Q#

Volání je přesně to, co se volá a spouští Q# .
Nicméně vyžaduje několik dalších přídavků, které tvoří úplný `*.qs` Q# soubor.

Všechny Q# typy a výzvy (které definujete i u těchto vnitřních objektů) jsou definovány v rámci *oborů názvů*, které poskytují každý úplný název, na který lze odkazovat.

Například [`H`](xref:Microsoft.Quantum.Intrinsic.H) [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operace a se nacházejí v [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) oborech názvů a (součást [ Q# standardních knihoven](xref:microsoft.quantum.libraries.standard.intro)).
V takovém případě mohou být vždy volány prostřednictvím jejich *úplných* názvů, `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` ale vždy to vede k tomu, že by to vedlo k velmi zbytečnému kódu.

Místo toho `open` příkazy umožňují volat odkazování pomocí výstižnější zkratky, jak jsme udělali v těle operace výše.
Úplný Q# soubor obsahující naši operaci by se tedy sestávat z definice vlastního oboru názvů, otevřením oborů názvů pro ty, které používá naše operace, a pak naší operace:

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> Obory názvů lze také *aliasovat* při otevření, což může být užitečné v případě konfliktu názvů volat/typu ve dvou oborech názvů.
> Například můžeme použít `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` výše a potom zavolat `H` prostřednictvím `NamespaceWithH.H(<qubit>)` .

> [!NOTE]
> Jedna výjimka pro všechny Toto je [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) obor názvů, který je vždy automaticky otevřen.
> Proto lze volat jako [`Length`](xref:Microsoft.Quantum.Core.Length) vždy použít přímo.

### <a name="running-on-target-machines"></a>Spuštění na cílových počítačích

Nyní se model obecného spuštění Q# programu bude jasný.

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

Za prvé, konkrétní spuštění, které se dá spustit, má přístup k jakýmkoli jiným volat a typům definovaným ve stejném oboru názvů.
Také k nim přistupuje z libovolné [ Q# knihovny](xref:microsoft.quantum.libraries), ale musí být odkazovány buď prostřednictvím jejich úplného názvu, nebo pomocí `open` příkazů popsaných výše.

Samostatně se pak spustí na *[cílovém počítači](xref:microsoft.quantum.machines)*.
Tyto cílové počítače můžou být skutečným hardwarem nebo s více simulátory, které jsou k dispozici jako součást QDK.
Pro naše účely je nejužitečnější cílový počítač instancí [simulátoru s plným stavem](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` který počítá chování programu, jako kdyby bylo spuštěno na počítači se systémem bezproblémového provozu.

Zatím jsme popsali, co se stane, když Q# se spustí konkrétní volat.
Bez ohledu na to, jestli Q# se používá v samostatné aplikaci nebo v hostitelském programu, je tento obecný proces více nebo méně stejný,---QDK, takže flexibilita.
Rozdíly mezi způsoby volání do vývojové sady pro plnění stavových prostředí se proto odhalují v *tom, jak* Q# se volá, aby se dala spustit, a v jakém způsobu se vrátí výsledky.
Přesněji řečeno, rozdíly obtéká:

- Označuje, který Q# volat lze spustit.
- Jak jsou k dispozici možné argumenty pro možnost použití
- Určení cílového počítače, na kterém se má spustit
- Jak se vrátí výsledky

Nejdřív se podíváme na to, jak se to dělá u Q# samostatné aplikace z příkazového řádku, a pak budete pokračovat v používání hostitelských programů Pythonu a C#.
Vyhrazujeme si samostatnou aplikaci Q# Jupyter poznámkových bloků jako poslední, protože na rozdíl od prvních tří nezáleží na tom, že se jedná o primární funkce na střed místního Q# souboru.

> [!NOTE]
> I když ho v těchto příkladech neilustruje, jedno společné mezi metodami spuštění je, že všechny zprávy vytištěné zevnitř Q# programu ( [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) například uživatelem [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) ) budou obvykle vždy vytištěny do příslušné konzoly.

## <a name="no-locq-from-the-command-prompt"></a>Q# z příkazového řádku
Jedním z nejjednodušších způsobů, jak začít psát Q# programy, je zabránit tomu, aby se nemuseli starat o samostatné soubory a druhý jazyk.
Pomocí Visual Studio Code nebo sady Visual Studio s rozšířením QDK umožňuje bezproblémové pracovní postup, ve kterém se spouští Q# volat jenom z jednoho Q# souboru.

V tomto případě budeme program spouštět tak, že zadáte

```dotnetcli
dotnet run
```

na příkazovém řádku.
Nejjednodušší pracovní postup je v případě, že je umístění adresáře terminálu stejné jako Q# soubor, který je možné snadno zpracovávat společně s Q# úpravami souborů pomocí integrovaného terminálu v vs Code, například.
[ `dotnet run` Příkaz](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) však akceptuje mnoho možností a program lze také spustit z jiného umístění pouhým poskytnutím `--project <PATH>` umístění Q# souboru.


### <a name="add-entry-point-to-no-locq-file"></a>Přidat vstupní bod do Q# souboru

Většina Q# souborů bude obsahovat více než jednu naužitečnou, takže je potřeba, aby kompilátor věděl, *který* volat, aby se spouštěl při zadání `dotnet run` příkazu.
To se provádí jednoduchou změnou Q# samotného souboru: 
    - Přidejte řádek, který `@EntryPoint()` je přímo před volat.

Náš soubor výše by se proto stal
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

Nyní volání `dotnet run` z příkazového řádku vede ke `MeasureSuperposition` spuštění a vrácená hodnota je následně vytištěna přímo na terminálu.
Zobrazí se buď `One` nebo `Zero` vytištěno. 

Mějte na paměti, že pokud máte více než jedno navýšení volat, `MeasureSuperposition` bude spuštěno.
Kromě toho není k dispozici žádný problém, pokud vaše volat obsahuje [dokumentační komentáře](xref:microsoft.quantum.qsharp.comments#documentation-comments) před jeho deklarací, `@EntryPoint()` atribut lze jednoduše umístit nad něj.

### <a name="callable-arguments"></a>Volat argumenty

Zatím jsme se považovali jenom na operace, které přebírají žádné vstupy.
Předpokládejme, že jsme chtěli provést podobnou operaci, ale na více qubits---počet, který je k dispozici jako argument.
Taková operace by mohla být zapsána jako
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
kde vrácená hodnota je pole výsledků měření.
Všimněte si, že [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) a [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) jsou [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) v [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) oborech názvů a, vyžadování dalších `open` příkazů pro každý z nich.

Pokud přesouváte `@EntryPoint()` atribut tak, aby předchází této nové operaci (Všimněte si, že může být pouze jeden řádek v souboru), pokus o jeho spuštění s jednoduchým `dotnet run` výsledkem je chybová zpráva s informací o tom, jaké další možnosti příkazového řádku jsou vyžadovány a jak je vyjádřit.

Obecný formát příkazového řádku je ve skutečnosti `dotnet run [options]` a k dispozici jsou argumenty, které jsou zde k dispozici.
V tomto případě `n` chybí argument a ukazuje, že je nutné zadat možnost `-n <n>` . Pro spuštění `MeasureSuperpositionArray` pro `n=4` qubits proto používáme

```dotnetcli
dotnet run -n 4
```

získávání výstupu podobného

```output
[Zero,One,One,One]
```

Tento kurz rozšiřuje na více argumentů.

> [!NOTE]
> Názvy argumentů definované v `camelCase` jsou mírně změněny kompilátorem tak, aby byly přijaty jako Q# vstupy. Například, pokud místo `n` , jsme použili název `numQubits` uvedený výše, a tento vstup by se zadal na příkazovém řádku pomocí `--num-qubits 4` místo `-n 4` .

Chybová zpráva taky obsahuje další možnosti, které se dají použít, včetně toho, jak změnit cílový počítač.

### <a name="different-target-machines"></a>Různé cílové počítače

Vzhledem k tomu, že výstupy z našich operací byly doposud očekávané výsledky jejich akce v reálném qubits, je jasné, že výchozí cílový počítač z příkazového řádku je plný stav simulátoru `QuantumSimulator` .
Dá se ale dát pokyn ke spuštění na konkrétním cílovém počítači s možností `--simulator` (nebo zkráceným `-s` ).

Můžete ho například spustit na [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

Vytištěný výstup je pak

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

Podrobnosti o tom, co tyto metriky naznačují, najdete v tématu věnovaném [Estimator prostředků: metriky se nahlásily](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).

### <a name="command-line-run-summary"></a>Souhrn spuštění příkazového řádku
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a>Jiné než Q# `dotnet run` Možnosti

Jak jsme se na tuto možnost krátce zmínili `--project` , [ `dotnet run` příkaz](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) také přijímá možnosti, které nesouvisí s argumenty, které lze Q# volat.
Pokud jsou zadány oba typy možností, `dotnet` musí být nejprve poskytnuty možnosti specifické pro, následované oddělovač `--` a Q# možnosti specifické pro.
Například zadání cesty spolu s číslem qubits pro operaci výše by bylo spuštěno prostřednictvím `dotnet run --project <PATH> -- -n <n>` .

## <a name="no-locq-with-host-programs"></a>Q# s hostitelskými programy

U našeho Q# souboru je alternativou k volání operace nebo funkce přímo z příkazového řádku použití *hostitelského programu* v jiném klasickém jazyce. Konkrétně to lze provést buď pomocí Pythonu, nebo jazyka .NET, jako je C# nebo F # (za účelem zkrácení budeme podrobnosti pouze C#).
K povolení interoperability je potřeba trochu dalších nastavení, ale tyto podrobnosti najdete v [pokynech k instalaci](xref:microsoft.quantum.install).

V kostce nyní tato situace zahrnuje soubor hostitelského programu (například `*.py` nebo `*.cs` ) ve stejném umístění jako náš Q# soubor.
Nyní je *hostitelský* program, který se spustí, a když je spuštěný, může volat konkrétní Q# operace a funkce ze Q# souboru.
Základem interoperability je Q# vytvoření obsahu Q# souboru přístupného pro hostitelský program, aby bylo možné je volat.

Jednou z hlavních výhod používání hostitelského programu je to, že klasická data vrácená Q# programem se pak dají dál zpracovat v jazyce hostitele.
Může se jednat o některé pokročilé zpracování dat (například něco, co se v nástroji nedá provést interně Q# ) a pak na základě těchto výsledků zavoláme další Q# akce nebo něco jednoduchého jako vykreslení Q# výsledků.

Tady se zobrazí obecné schéma a v následující části se podíváme na konkrétní implementace pro Python a C#. Ukázku použití hostitelského programu F # najdete v [ukázkách interoperability .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> `@EntryPoint()`Atribut používaný pro Q# aplikace nelze použít s hostitelskými programy.
> Pokud se nachází v souboru, který Q# Host volá, bude vyvolána chyba. 

Pro práci s různými hostitelskými programy nejsou k dispozici žádné změny `*.qs` Q# souboru.
Následující hostitelské programy implementují všechny práce se stejným Q# souborem:

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

Vyberte kartu odpovídající vašemu hostitelskému jazyku, který vás zajímá.

### <a name="python"></a>[Python](#tab/tabid-python)
Hostitelský program Pythonu je vytvořený takto:
1. Importujte `qsharp` modul, který registruje zavaděč modulu pro Q# interoperabilitu. 
    To umožňuje Q# , aby se obory názvů zobrazovaly jako moduly Pythonu, ze kterých můžeme "importovat" Q# .
    Všimněte si, že se nejedná o nepřímo Q# přizpůsobitelné metody, které jsou naimportovány, ale spíše jako zástupné procedury Pythonu, které umožňují
    Chovají se jako objekty tříd Pythonu. Metody na těchto objektech používáme k určení cílových počítačů, na které odesíláme operace při spuštění programu.

2. Naimportujte ty Q# , které budou v tomto případě přímo vyvolány--- `MeasureSuperposition` a `MeasureSuperpositionArray` .
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    Pomocí `qsharp` importovaného modulu můžete také naimportovat volatelné přímo z Q# oboru názvů knihoven.

3. V jakémkoli jiném kódu Pythonu teď můžete zavolat tyto výzvy na konkrétní cílové počítače a přiřadit jejich návrat k proměnným (Pokud vrátí hodnotu) pro další použití.

#### <a name="specifying-target-machines"></a>Určení cílových počítačů
Volání operace, která se má spustit na konkrétním cílovém počítači, se provádí prostřednictvím různých metod Pythonu u importovaného objektu.
Například `.simulate(<args>)` používá `QuantumSimulator` ke spuštění operace, zatímco `.estimate_resources(<args>)` to dělá na `ResourcesEstimator` .

#### <a name="passing-inputs-to-q"></a>Předání vstupů do Q\#
Argumenty pro Q# volat by měly být zadány ve formě argumentu klíčového slova, kde klíčové slovo je název argumentu v Q# definici volat.
To znamená, že `MeasureSuperpositionArray.simulate(n=4)` je platná, zatímco `MeasureSuperpositionArray.simulate(4)` by vyvolala chybu.

Proto hostitelský program Pythonu 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

Výsledkem bude výstup podobný následujícímu:

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a>Použití Q# kódu z jiných projektů nebo balíčků

Ve výchozím nastavení `import qsharp` příkaz načte všechny `.qs` soubory v aktuální složce a zpřístupní jejich Q# operace a funkce pro použití zevnitř skriptu Pythonu.

Chcete-li načíst Q# kód z jiné složky, [ `qsharp.projects` rozhraní API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) lze použít k přidání odkazu na `.csproj` soubor pro Q# projekt (tj. projekt, který odkazuje `Microsoft.Quantum.Sdk` ).
Tento příkaz zkompiluje všechny `.qs` soubory ve složce obsahující `.csproj` a jejích podsložkách. Bude také rekurzivně načítat jakékoli balíčky, na které se odkazuje přes `PackageReference` Q# , nebo `ProjectReference` na projekty, na které se odkazuje v tomto `.csproj` souboru.

Například následující kód Pythonu Importuje externí projekt, odkazuje na jeho cestu relativní vzhledem k aktuální složce a vyvolá jednu z jeho Q# operací:

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

Výsledkem bude výstup podobný následujícímu:

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

Chcete-li načíst externí balíčky obsahující Q# kód, použijte [ `qsharp.packages` rozhraní API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).

Pokud Q# kód v aktuální složce závisí na externích projektech nebo balíčcích, mohou se při spuštění zobrazit chyby `import qsharp` , protože závislosti ještě nebyly načteny.
Pokud chcete načíst požadované externí balíčky nebo Q# projekty v rámci `import qsharp` příkazu, ujistěte se, že složka se skriptem Pythonu obsahuje `.csproj` soubor, který odkazuje na `Microsoft.Quantum.Sdk` . V takovém `.csproj` případě přidejte vlastnost `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` do `<PropertyGroup>` . Tím se dá dát Q# k rekurzivnímu načtení libovolných `ProjectReference` `PackageReference` položek nebo nalezených v `.csproj` rámci `import qsharp` příkazu.

Například tady je jednoduchý `.csproj` soubor, který způsobí, že Q# se má automaticky načíst `Microsoft.Quantum.Chemistry` balíček:

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> V současné době `<IQSharpLoadAutomatically>` je tato vlastní vlastnost vyžadována v hostitelích Pythonu, ale v budoucnu se to může stát výchozím chováním pro `.csproj` soubor umístěný ve stejné složce jako skript Pythonu.

> [!NOTE]
> V současné době `<QsharpCompile>` je nastavení v rozhraní `.csproj` ignorováno hostiteli Pythonu a `.qs` `.csproj` jsou načteny a kompilovány všechny soubory ve složce (včetně podsložek). `.csproj`V budoucnu se zlepší podpora nastavení (další podrobnosti najdete v tématu [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) ).


### <a name="c"></a>[C#](#tab/tabid-csharp)

Hostitelský program v jazyce C# má více komponent a pracuje velmi pečlivě s některými komponentami QDK, jako jsou například simulátory, které jsou samy postaveny na C#.

Q#Kompilátor tady funguje tak, že generuje ekvivalentně pojmenovaný obor názvů C# z Q# oboru názvů v našem Q# souboru.
Dále vygeneruje ekvivalentní název třídy jazyka C# pro každý z určených volání Q# nebo typů, které jsou definovány v rámci.

Nejprve zpřístupníme všechny třídy, které jsou k dispozici v našem hostitelském programu s `using` příkazy, které jsou zhruba analagous na `open` příkazy v našem Q# souboru:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (for example, QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

Dále deklarujeme náš obor názvů C#, několik dalších bitů a částí (viz úplný blok kódu níže) a pak jakékoli klasické programování, které bychom chtěli (například výpočetních argumentů pro Q# volat).
Ta není v našem případě nutná, ale příklad takového použití najdete v  [ukázce interoperability .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).

#### <a name="target-machines"></a>Cílové počítače

Když se vrátíte zpátky Q# , musíme vytvořit instanci libovolného cílového počítače, na které budeme provozovat.

```csharp
            using var sim = new QuantumSimulator();
```

Použití jiných cílových počítačů je stejně jednoduché jako vytvoření instance jiného, přestože způsob, jak to udělat, a zpracování vrácených změn může být mírně odlišné.
V případě zkrácení se [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) pro teď používáme a zařadíme [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [níže](#including-the-resources-estimator).

Každá třída jazyka C# vygenerovaná z Q# operací má `Run` metodu, první argument, který musí být instancí cílového počítače.
Takže pokud chcete spustit `MeasureSuperposition` v `QuantumSimulator` , používáme `MeasureSuperposition.Run(sim)` .
Vrácené výsledky lze následně přiřadit proměnným v jazyce C#:

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> `Run`Metoda je spouštěna asynchronně, protože se jedná o případ reálného hardwaru s `await` více procesory, a proto klíčové slovo zablokuje další zpracování až do dokončení úkolu.

Pokud je Q# to možné, že k dispozici nejsou žádné návraty (například má návratový typ `Unit` ), může být spuštění provedeno stejným způsobem bez přiřazení k proměnné.
V takovém případě by se celý řádek měl jednoduše skládat z 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>Arguments

Jakékoli argumenty, které lze Q# volat, jsou jednoduše předány jako další argumenty po cílovém počítači.
Proto výsledky z `MeasureSuperpositionArray` `n=4` qubits by se načetly prostřednictvím 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

Úplný hostitelský program v C# by mohl vypadat takto

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

V umístění souboru jazyka C# lze hostitelský program spustit z příkazového řádku zadáním
```dotnetcli
dotnet run
```
v tomto případě se zobrazí výstup napsaný do konzoly podobně jako 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> Z důvodu interoperability kompilátoru s obory názvů můžeme Alternativně zpřístupnit Q# k dispozici bez `using NamespaceName;` příkazu a jednoduše tak, aby se k němu přishodoval název oboru názvů C#.
> To znamená nahrazením `namespace host` pomocí `namespace NamespaceName` .

#### <a name="including-the-resources-estimator"></a>Zahrnutí prostředků Estimator

[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Pro načtení výstupu vyžaduje poněkud odlišnou implementaci.

Nejprve místo toho, aby se vytvořila instance jako proměnná s `using` příkazem (stejně jako v případě `QuantumSimulator` ), je více přímo vytvořena instance objektů třídy prostřednictvím

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

Všimněte si, že místo jediného cílového simulátoru, který má být použit více Q# operacemi, jsme pro každý z nich nastavili instanci. Důvodem je to, že při použití jako cílové počítače jsou změněny samotné objekty a jejich výsledky lze následně načíst pomocí metody třídy `.ToTSV()` .

Pro spuštění operací na odhady prostředků používáme

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
a potom výsledky načtěte jako hodnoty hodnot TSV (tabulátor-revalues) s `estimatorSingleQ.ToTSV()` a `estimatorMultiQ.ToTSV()` .

Úplný hostitelský program v jazyce C#, který používá jak `QuantumSimulator` a `ResourcesEstimator` může mít podobu:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


což by znamenalo výstup podobný

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="no-locq-jupyter-notebooks"></a>Q# Jupyter poznámkové bloky
Q# Jupyter poznámkové bloky využívají jádro I Q# , které umožňuje definovat, kompilovat a spouštět Q# volat v jednom poznámkovém bloku---všech společně s pokyny, poznámkami a dalšími obsahy.
To znamená, že přestože je možné importovat a používat obsah `*.qs` Q# souborů, nejsou v modelu spuštění nutné.

Zde podrobně pomůžeme, jak spustit Q# výše uvedené operace, ale obecnější Úvod k používání Q# notebooků Jupyter je k dispozici na stránce [Úvod do Q# a Jupyter poznámkových blocích](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).

### <a name="defining-operations"></a>Definování operací

V Q# Jupyter notebook zadáte Q# kód stejně jako v rámci oboru názvů Q# souboru.

Proto můžeme povolit přístup k volat ze [ Q# standardních knihoven](xref:microsoft.quantum.libraries.standard.intro) s `open` příkazy pro jejich příslušné obory názvů.
Po spuštění buňky s takovým příkazem jsou definice z těchto oborů názvů dostupné v celém pracovním prostoru.

> [!NOTE]
> Pro operace definované [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) v [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) [`H`](xref:Microsoft.Quantum.Intrinsic.H) [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) rámci buněk v Q# poznámkových blocích Jupyter se budou automaticky přivolat z Microsoft. probíhajících. vnitřní a Microsoft.
> Nicméně to není pravdivé pro kód převedený z externích Q# zdrojových souborů (proces zobrazený v [úvodu do Q# a Jupyter poznámkových bloků](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)). 
> 

Podobně definování operací vyžaduje pouze zápis Q# kódu a spuštění buňky.

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="773">

Výstup pak obsahuje seznam operací, které je možné volat z budoucích buněk.

### <a name="target-machines"></a>Cílové počítače

Funkce pro spouštění operací na konkrétních cílových počítačích je poskytována prostřednictvím [ Q# příkazů I Magic](xref:microsoft.quantum.guide.quickref.iqsharp).
Například využívá `%simulate` `QuantumSimulator` a `%estimate` používá `ResourcesEstimator` :

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a Q# operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a>Předávání vstupů do funkcí a operací

Aby Q# bylo možné do operací předat vstupy, argumenty lze předat jako `key=value` páry k příkazu Spustit Magic.
Takže pokud chcete spustit `MeasureSuperpositionArray` se čtyřmi qubits, můžeme spustit `%simulate MeasureSuperpositionArray n=4` :

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a Q# operation with arguments" width="773">

Tento model lze použít podobně jako `%estimate` a jiné příkazy pro spuštění.

### <a name="using-no-locq-code-from-other-projects-or-packages"></a>Použití Q# kódu z jiných projektů nebo balíčků

Ve výchozím nastavení Q# Jupyter notebook načítá všechny `.qs` soubory v aktuální složce a zpřístupňuje jejich Q# operace a funkce pro použití v rámci poznámkového bloku. [ `%who` Příkaz Magic](xref:microsoft.quantum.iqsharp.magic-ref.who) vypíše všechny aktuálně dostupné Q# operace a funkce.

Chcete-li načíst Q# kód z jiné složky, lze pomocí [ `%project` příkazu Magic](xref:microsoft.quantum.iqsharp.magic-ref.project) přidat odkaz na `.csproj` soubor pro Q# projekt (tj. projekt, který odkazuje na `Microsoft.Quantum.Sdk` ). Tento příkaz zkompiluje všechny `.qs` soubory ve složce obsahující `.csproj` (a podsložek). Bude také rekurzivně načítat jakékoli balíčky, na které se odkazuje přes `PackageReference` Q# , nebo `ProjectReference` na projekty, na které se odkazuje v tomto `.csproj` souboru. 

Například následující buňky simulují Q# operaci z externího projektu, kde je odkazováno na cestu k projektu vzhledem k aktuální složce:

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a Q# operation from an external project" width="773">

Pokud chcete načíst externí balíčky obsahující Q# kód, použijte [ `%package` příkaz Magic](xref:microsoft.quantum.iqsharp.magic-ref.package).
Načtení balíčku také zpřístupní všechny vlastní příkazy Magic nebo zobrazovací kodéry, které jsou obsaženy ve všech sestaveních, která jsou součástí balíčku.

Pokud chcete načíst externí balíčky nebo Q# projekty v průběhu inicializace poznámkového bloku, ujistěte se, že složka Poznámkový blok obsahuje `.csproj` soubor, který odkazuje na `Microsoft.Quantum.Sdk` . V takovém `.csproj` případě přidejte vlastnost `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` do `<PropertyGroup>` . Tím se dá dát Q# k rekurzivnímu načítání libovolných `ProjectReference` `PackageReference` položek nebo nalezených v `.csproj` době načítání poznámkového bloku.

Například tady je jednoduchý `.csproj` soubor, který způsobí, že Q# se má automaticky načíst `Microsoft.Quantum.Chemistry` balíček:

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> V současné době `<IQSharpLoadAutomatically>` je tato vlastní vlastnost požadována Q# Jupyter notebook hostiteli, ale v budoucnu se to může stát výchozím chováním pro `.csproj` soubor umístěný ve stejné složce jako soubor poznámkového bloku.

> [!NOTE]
> V současné době `<QsharpCompile>` je nastavení v rozhraní `.csproj` ignorováno Q# Jupyter notebook hostitelé a všechny `.qs` soubory ve složce `.csproj` (včetně podsložek) jsou načteny a kompilovány. `.csproj`V budoucnu se zlepší podpora nastavení (další podrobnosti najdete v tématu [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) ).
