---
title: 'Způsoby spuštění programu Q #'
description: 'Přehled různých způsobů spouštění programů Q #. Z příkazového řádku, poznámkových bloků Q # Jupyter a klasických hostitelských programů v Pythonu nebo v jazyce .NET.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
ms.openlocfilehash: 132c138d7c392ed2b4bd3d0079180b68adae4cfc
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2020
ms.locfileid: "85887656"
---
# <a name="ways-to-run-a-q-program"></a>Způsoby spuštění programu Q #

Jednou z největších silou pro vývojová prostředí pro životní prostředí je jeho flexibilita napříč platformami a vývojovým prostředím.
To ale také znamená, že noví uživatelé Q # můžou najít zaměňování nebo zahlcení řadou možností, které najdete v [instalační příručce](xref:microsoft.quantum.install).
Na této stránce vysvětlete, co se stane, když se spustí program Q #, a porovnejte různé způsoby, jak to uživatelé můžou udělat.

Zásadním rozdílem je, že Q # lze spustit:
- jako samostatná aplikace, kde Q # je jediný jazyk, který je součástí programu a který je vyvolán přímo. Do této kategorie ve skutečnosti patří dvě metody:
  - rozhraní příkazového řádku
  - Aplikace Jupyter Notebook v Q#
- s dalším *hostitelským programem*, který je napsán v Pythonu nebo v jazyce .NET (např. C# nebo F #), který potom vyvolá program a může pokračovat ve zpracování vrácených výsledků.

Abychom těmto procesům a jejich rozdílům nejlépe pochopili, Uvažujme o jednoduchém programu Q # a porovnejte způsob, jakým je možné ho spustit.

## <a name="basic-q-program"></a>Základní program Q #

Základní program pro vystavování se může skládat z přípravy qubit do stejné pozice stavů $ \ket {0} $ a $ \ket {1} $, měření a vrácení výsledku, který bude náhodně buď jedna z těchto dvou stavů, se stejnou pravděpodobností.
Tento proces je skutečně v jádru pro rychlý Start [generátoru náhodných čísel](xref:microsoft.quantum.quickstarts.qrng) .

V Q # by to bylo provedeno následujícím kódem:

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

Samotný kód však nelze spustit pomocí Q #.
V takovém případě musí sestavovat tělo [operace](xref:microsoft.quantum.guide.basics#q-operations-and-functions), která se pak spustí při volání---, a to buď přímo, nebo jinou operací. Proto můžete napsat operaci následujícího formuláře:
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
Definovali jste operaci, `MeasureSuperposition` která nepřijímá žádné vstupy a vrací hodnotu typu [Result](xref:microsoft.quantum.guide.types).

I když příklady na této stránce sestávají jenom s *operacemi*q #, všechny koncepty, které budeme projednávat, se budou týkat i *funkcí*q #, a proto je budeme v souhrnně *označovat jako možné*. Jejich rozdíly jsou popsány v tématu [základní informace o funkci Q #: operace a funkce](xref:microsoft.quantum.guide.basics#q-operations-and-functions)a další informace o jejich definování najdete v tématu [operace a funkce](xref:microsoft.quantum.guide.operationsfunctions).

### <a name="callable-defined-in-a-q-file"></a>Navolatelné v souboru Q #

Volání je přesně to, co se volá a spouští se Q #.
Nicméně vyžaduje několik dalších přídavků, které obsahují úplný `*.qs` soubor Q #.

Všechny typy Q # a volatelné (ty, které definujete i u těchto vnitřních jazyků) jsou definovány v rámci *oborů názvů*, které poskytují každý úplný název, na který lze následně odkazovat.

Například [`H`](xref:microsoft.quantum.intrinsic.h) [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) operace a se nacházejí v [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) oborech názvů a (součást [standardních knihoven Q #](xref:microsoft.quantum.qsharplibintro)).
V takovém případě mohou být vždy volány prostřednictvím jejich *úplných* názvů, `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` ale vždy to vede k tomu, že by to vedlo k velmi zbytečnému kódu.

Místo toho `open` příkazy umožňují volat odkazování pomocí výstižnější zkratky, jak jsme udělali v těle operace výše.
Úplný soubor Q # obsahující naši operaci se proto skládá z definování vlastního oboru názvů, otevření oborů názvů pro ty, které používají naši operaci, a pak naší operace:

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
> Jedna výjimka pro všechny Toto je [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) obor názvů, který je vždy automaticky otevřen.
> Proto lze volat jako [`Length`](xref:microsoft.quantum.core.length) vždy použít přímo.

### <a name="execution-on-target-machines"></a>Spouštění na cílových počítačích

Nyní bude obecný model spuštění programu Q # jasný.

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

Za prvé, konkrétní spuštění, které se má spustit, má přístup k jakýmkoli jiným přívolat a typům definovaným ve stejném oboru názvů.
Také k nim přistupuje z libovolné [knihovny Q #](xref:microsoft.quantum.libraries), ale musí být odkazovány buď prostřednictvím jejich úplného názvu, nebo pomocí `open` příkazů popsaných výše.

Sama se pak spustí na *[cílovém počítači](xref:microsoft.quantum.machines)*.
Tyto cílové počítače můžou být skutečným hardwarem nebo s více simulátory, které jsou k dispozici jako součást QDK.
Pro naše účely je nejužitečnější cílový počítač instancí [simulátoru s plným stavem](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` který počítá chování programu, jako kdyby bylo spuštěno na počítači se systémem, který je bezproblémový.

Zatím jsme popsali, co se stane, když se spustí konkrétní Q # volat.
Bez ohledu na to, zda je v samostatné aplikaci nebo v hostitelském programu používáno Q #, je tento obecný proces více nebo méně stejný,---QDK, tedy flexibilitu.
Rozdíly mezi různými způsoby volání do vývojového prostředí pro plnění obsahu si proto samy odhalí, *jak* je volání Q # Called provedeno a v jakém způsobem jsou vráceny výsledky.
Přesněji řečeno, rozdíly obtéká kolem 
1. označuje, kterou hodnotu Q # volat se má provést.
2. jak jsou k dispozici možné argumenty pro možnost použití,
3. zadání cílového počítače, na kterém se má spustit, a
4. způsob, jakým jsou vráceny výsledky.

Nejdřív se podíváme na to, jak se to dělá pomocí samostatné aplikace Q # z příkazového řádku, a pak pokračujte pomocí hostitelských programů Pythonu a C#.
Vyhrazujeme si samostatnou aplikaci poznámkových bloků Q # Jupyter, protože na rozdíl od prvních tří nezáleží na tom, že se jedná o místní funkce na střed souboru Q #.

> [!NOTE]
> I když ho v těchto příkladech neilustruje, jedná se o jeden společný vztah mezi metodami spuštění, protože všechny zprávy vytištěné z programu Q # (například v případě [`Message`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) , že) se obvykle vždy vytisknou do příslušné konzoly.

## <a name="q-from-the-command-line"></a>Q # z příkazového řádku
Jedním z nejjednodušších způsobů, jak začít psát do programu Q #, je zabránit tomu, abyste se mohli zcela starat o samostatné soubory a druhý jazyk.
Pomocí Visual Studio Code nebo sady Visual Studio s rozšířením QDK umožňuje bezproblémové pracovní postup, při kterém se spustí Q #, který se dá volat jenom z jednoho souboru Q #.

V tomto případě budeme vyvolávat spuštění programu tím, že zadáte
```dotnetcli
dotnet run
```
na příkazovém řádku.
Nejjednodušší pracovní postup je v případě, že je umístění adresáře terminálu stejné jako soubor Q #, který je možné snadno zpracovat vedle úprav souborů Q # pomocí integrovaného terminálu v VS Code.
[ `dotnet run` Příkaz](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) však akceptuje mnoho možností a program lze také spustit z jiného umístění pouhým poskytnutím `--project <PATH>` umístění souboru Q #.


### <a name="add-entry-point-to-q-file"></a>Přidat vstupní bod do souboru Q #

Většina souborů Q # bude obsahovat více než jednu vykonatelné, takže je potřeba, aby kompilátor věděl, *který* volat, aby se spustil při zadání `dotnet run` příkazu.
To se provádí jednoduchou změnou samotného souboru Q #: 
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

Nyní volání `dotnet run` z příkazového řádku vede ke `MeasureSuperposition` spuštění a vrácená hodnota je poté vytištěna přímo na terminálu.
Zobrazí se buď `One` nebo `Zero` vytištěno. 

Mějte na paměti, že pokud máte více než jedno navýšení volat, `MeasureSuperposition` bude spuštěno.
Kromě toho není k dispozici žádný problém, pokud vaše volat obsahuje [dokumentační komentáře](xref:microsoft.quantum.guide.filestructure#documentation-comments) před jeho deklarací, `@EntryPoint()` atribut lze jednoduše umístit nad něj.

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
Všimněte si, že [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) a [`ForEach`](xref:microsoft.quantum.arrays.foreach) jsou [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) v [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) oborech názvů a, vyžadování dalších `open` příkazů pro každý z nich.

Pokud přesouváme `@EntryPoint()` atribut tak, aby předcházel této nové operaci (Všimněte si, že v souboru může být jenom jeden řádek), pokus o jeho spuštění s jednoduchým `dotnet run` výsledkem je chybová zpráva, která indikuje, co je potřeba pro další možnosti příkazového řádku, a jak je vyjádřit.

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
> Názvy argumentů definované v `camelCase` jsou mírně změněny kompilátorem, aby byly přijaty jako vstupy Q #. Například, pokud místo `n` , jsme použili název `numQubits` uvedený výše, a tento vstup by se zadal na příkazovém řádku pomocí `--num-qubits 4` místo `-n 4` .

Chybová zpráva taky obsahuje další možnosti, které se dají použít, včetně toho, jak změnit cílový počítač.

### <a name="different-target-machines"></a>Různé cílové počítače

Vzhledem k tomu, že výstupy z našich operací byly doposud očekávané výsledky jejich akce v reálném qubits, je jasné, že výchozí cílový počítač z příkazového řádku je quauntum simulátor `QuantumSimulator` .
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

### <a name="command-line-execution-summary"></a>Souhrn spuštění příkazového řádku
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-q-dotnet-run-options"></a>Možnosti bez Q # `dotnet run`

Jak jsme se na tuto možnost krátce zmínili `--project` , [ `dotnet run` příkaz](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) také přijímá možnosti, které nesouvisí s argumenty volat v parametru Q #.
Pokud zadáváte oba druhy možností, `dotnet` musí být nejprve zadány možnosti specifické pro konkrétní parametry, následované oddělovač `--` a pak parametry specifické pro Q #.
Například specifiying cestu spolu s číslem qubits pro operaci výše, kterou by bylo provedeno prostřednictvím `dotnet run --project <PATH> -- -n <n>` .

## <a name="q-with-host-programs"></a>Q # s hostitelskými programy

S naším souborem Q # je alternativou pro volání operace nebo funkce přímo z příkazového řádku použití *hostitelského programu* v jiném klasickém jazyce. Konkrétně to lze provést buď pomocí Pythonu, nebo jazyka .NET, jako je C# nebo F # (za účelem zkrácení budeme podrobnosti pouze C#).
K povolení interoperability je potřeba trochu dalších nastavení, ale tyto podrobnosti najdete v [pokynech k instalaci](xref:microsoft.quantum.install).

V kostce nyní tato situace zahrnuje soubor hostitelského programu (například `*.py` nebo `*.cs` ) ve stejném umístění jako náš soubor Q #.
Nyní je *hostitelský* program, který se spustí, a v průběhu jeho provádění může volat konkrétní operace Q # a funkce ze souboru q #.
Základ interoperability je založen na kompilátoru Q # vytvoření obsahu souboru Q # přístupného pro hostitelský program, aby bylo možné je volat.

Jednou z hlavních výhod používání hostitelského programu je to, že klasická data vrácená programem Q # je pak možné dále zpracovat v jazyce hostitele.
Může se jednat o některé pokročilé zpracování dat (například něco, co se v Q # nedaří provést interně) a potom na základě těchto výsledků zavolat další akce Q # nebo něco jednoduchého jako vykreslení výsledků Q #.

Tady se zobrazí obecné schéma a v následující části se podíváme na konkrétní implementace pro Python a C#. Ukázku použití hostitelského programu F # najdete v [ukázkách interoperability .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> `@EntryPoint()`Atribut použitý pro aplikace příkazového řádku Q # nelze použít s hostitelskými programy.
> Pokud se objeví v souboru Q #, který volá hostitel, bude vyvolána chyba. 

Pro práci s různými hostitelskými programy nejsou v souboru Q # vyžadovány žádné změny `*.qs` .
Následující hostitelské programy implementují všechny práce se stejným souborem Q #:

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
1. Importujte `qsharp` modul, který registruje zavaděč modulů pro interoperabilitu Q #. 
    To umožňuje, aby se obory názvů Q # zobrazovaly jako moduly Pythonu, ze kterých můžeme "importovat" Q # volat.
    Všimněte si, že se nejedná o vlastní volání Q #, která se naimportují, ale namísto zástupných procedur v Pythonu, které jim umožňují zavolat.
    Ty se pak chovají jako objekty tříd Pythonu, na kterých používáme metody k určení cílových počítačů k odeslání operace k provedení.

2. Naimportují se volání Q #, která v tomto případě budeme v tomto případě volat přímo--- `MeasureSuperposition` a `MeasureSuperpositionArray` .
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    Pomocí `qsharp` importovaného modulu můžete také naimportovat volatelné přímo z oboru názvů knihovny Q #.

3. V jakémkoli jiném kódu Pythonu teď můžete zavolat tyto výzvy na konkrétní cílové počítače a přiřadit jejich návrat k proměnným (Pokud vrátí hodnotu) pro další použití.

#### <a name="specifying-target-machines"></a>Určení cílových počítačů
Volání operace, která se má spustit na konkrétním cílovém počítači, se provádí prostřednictvím různých metod Pythonu u importovaného objektu.
Například `.simulate(<args>)` používá `QuantumSimulator` ke spuštění operace, zatímco `.estimate_resources(<args>)` to dělá na `ResourcesEstimator` .

#### <a name="passing-inputs-to-q"></a>Předání vstupů do Q\#
Argumenty pro parametr Q # volat by měly být zadány ve formě argumentu klíčového slova, kde klíčové slovo je název argumentu v definici Q # volat.
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

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[C#](#tab/tabid-csharp)

Hostitelský program v jazyce C# má více komponent a pracuje velmi pečlivě s některými komponentami QDK, jako jsou například simulátory, které jsou samy postaveny na C#.

Kompilátor Q # zde funguje tak, že generuje ekvivalentně pojmenovaný obor názvů jazyka C# z oboru názvů Q # v našem souboru Q #.
Dále vygeneruje ekvivalentní název třídy jazyka C# pro každé volání nebo typy, které jsou definovány v jazyce Q.

Nejprve zpřístupníme všechny třídy, které jsou v našem hostitelském programu k dispozici s `using` příkazy, které jsou zhruba analagous na `open` příkazy v našem souboru Q #:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

Dále deklarujeme náš obor názvů C#, několik dalších bitů a částí (viz úplný blok kódu níže) a pak jakékoli klasické programování, které bychom chtěli (například výpočetní argumenty pro volat pro Q #).
Ta není v našem případě nutná, ale příklad takového použití najdete v [ukázce interoperability .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).

#### <a name="target-machines"></a>Cílové počítače

Když se vrátíte zpět k verzi Q #, musíme vytvořit instanci libovolného cílového počítače, na které budeme provádět operace.

```csharp
            using var sim = new QuantumSimulator();
```

Použití jiných cílových počítačů je stejně jednoduché jako vytvoření instance jiného, přestože způsob, jak to udělat, a zpracování vrácených změn může být mírně odlišné.
V případě zkrácení se [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) pro teď používáme a zařadíme [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [níže](#including-the-resources-estimator).

Každá třída jazyka C# vygenerovaná z operací Q # má `Run` metodu, jejímž prvním argumentem musí být instance cílového počítače.
Takže pokud chcete spustit `MeasureSuperposition` v `QuantumSimulator` , používáme `MeasureSuperposition.Run(sim)` .
Vrácené výsledky lze následně přiřadit proměnným v jazyce C#:

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> `Run`Metoda je prováděna asynchronně, protože se jedná o případ reálného hardwaru s `await` více jádry, a proto klíčové slovo zablokuje další provádění až do dokončení úkolu.

Pokud funkce Q # volat neobsahuje žádné vratky (tj. má návratový typ `Unit` ), může být provádění stále provedeno stejným způsobem bez přiřazení k proměnné.
V takovém případě by se celý řádek měl jednoduše skládat z 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>Arguments

Jakékoli argumenty pro volat v Q # jsou jednoduše předány jako další argumenty grafice cílový počítač.
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
> S ohledem na interoperabilitu kompilátoru s obory názvů můžeme Alternativně zpřístupnit naši adresu Q #, která je k dispozici bez `using NamespaceName;` příkazu, a jednoduše odpovídat názvu oboru názvů C#.
> To znamená nahrazením `namespace host` pomocí `namespace NamespaceName` .

#### <a name="including-the-resources-estimator"></a>Zahrnutí prostředků Estimator

[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Pro načtení výstupu vyžaduje poněkud odlišnou implementaci.

Nejprve místo toho, aby se vytvořila instance jako proměnná s `using` příkazem (stejně jako v případě `QuantumSimulator` ), je více přímo vytvořena instance objektů třídy prostřednictvím

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

Všimněte si, že místo jednoho cílového simulátoru, který má být použit více operacemi Q #, byl pro každou instanci vytvořen jeden. Důvodem je to, že při použití jako cílové počítače jsou změněny samotné objekty a jejich výsledky lze následně načíst pomocí metody třídy `.ToTSV()` .

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

## <a name="q-jupyter-notebooks"></a>Aplikace Jupyter Notebook v Q#
Q # Jupyter poznámkové bloky využívají jádro SWEETIQ #, které umožňuje definovat, kompilovat a spouštět Q # volat v jednom poznámkovém bloku---všech společně s pokyny, poznámkami a dalšími obsahy.
To znamená, že přestože je možné importovat a používat obsah `*.qs` souborů Q #, nejsou v modelu spuštění nutné.

Tady si podrobně podíváme, jak spustit výše uvedené operace Q #, ale v [úvodu do notebooků q # a Jupyter](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)je k dispozici širší Úvod k použití notebooků q # Jupyter.

### <a name="defining-operations"></a>Definování operací

V Jupyter Notebook Q # zadáte kód Q # stejně jako v rámci oboru názvů souboru Q #.

Proto můžeme povolit přístup k volat z [standartní knihovny Q #](xref:microsoft.quantum.qsharplibintro) s `open` příkazy pro jejich příslušné obory názvů.
Po spuštění buňky s takovým příkazem jsou definice z těchto oborů názvů dostupné v celém pracovním prostoru.

> [!NOTE]
> K operacím definovaným v [Microsoft.Quantum.Intrinsic](xref:microsoft.quantum.intrinsic) rámci buněk v [Microsoft.Quantum.Canon](xref:microsoft.quantum.canon) [`H`](xref:microsoft.quantum.intrinsic.h) [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) poznámkových blocích Q # Jupyter se budou automaticky přivolat z Microsoft. probíhají. vnitřní a Microsoft.. Canon (např. a).
> To však není pravdivé pro kód, který je součástí z externích zdrojových souborů Q # (proces zobrazený v [úvodu do poznámkových bloků q # a Jupyter](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)). 
> 

Podobně definování operací vyžaduje pouze zápis kódu Q # a spuštění buňky.

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

Výstup pak obsahuje seznam operací, které je možné volat z budoucích buněk.

### <a name="target-machines"></a>Cílové počítače

Funkce pro spouštění operací na konkrétních cílových počítačích se poskytuje prostřednictvím [příkazů sweetiq # Magic](xref:microsoft.quantum.guide.quickref.iqsharp).
Například využívá `%simulate` `QuantumSimulator` a `%estimate` používá `ResourcesEstimator` :

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a>Předávání vstupů do funkcí a operací

V současné době se příkazy pro spuštění Magic dají použít jenom s operacemi, které nevyužívají žádné argumenty. Takže aby bylo možné spustit `MeasureSuperpositionArray` , musíme definovat operaci "Obálka", která pak zavolá operaci s argumenty:

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

Tuto operaci je možné použít podobně jako v rámci `%estimate` a dalších příkazů pro spuštění.
