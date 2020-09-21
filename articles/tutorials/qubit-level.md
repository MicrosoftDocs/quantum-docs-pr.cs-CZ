---
title: Zápis a simulace programů na úrovni qubit v nástroji Q#
description: Podrobný návod k psaní a simulaci programu pro období, který funguje na úrovni jednotlivých qubit
author: gillenhaalb
ms.author: a-gibec
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0dbeee8e092c830576ba8f79733035cdeeac11de
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834954"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a>Kurz: zápis a simulace programů qubit na úrovni Q\#

Vítá vás kurz pro vývoj všech automobilů při psaní a simulaci základního programu pro vyhlašování do více období, který funguje na jednotlivých qubits. 

I když Q# byl primárně vytvořen jako programovací jazyk vysoké úrovně pro velké množství procesorových procesorů, může to být stejně snadné použít k prozkoumávání nižší úrovně programů, které jsou určeny k tomu, že přímo řeší konkrétní qubits.
Flexibilita Q# umožňuje uživatelům přístup k systémům z nedostatku z jakékoli takové úrovně abstrakce a v tomto kurzu jsme podrobněi qubits sami.
Konkrétně se podívejme na digestoři [Fourierova transformace](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), která je nedílnou součástí mnoha větších algoritmů.

Všimněte si, že tento přehled zpracování informací o nedostatku na více procesorů je často popsaný v části "[okruhy](xref:microsoft.quantum.concepts.circuits)v obdobích", což představuje sekvenční použití bran na konkrétní qubits systému.

Operace typu Single-a qubit, které se účtují sekvenčně, se proto dají snadno reprezentovat v "diagramu okruhu".
V našem případě definujeme Q# operaci, která provede úplnou qubitou transformaci na tři procesory, která má následující reprezentaci jako okruh:

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a>Požadavky

* [Nainstalujte](xref:microsoft.quantum.install) sadu pro vývoj pro práci s více jazyky pomocí vašeho preferovaného jazykového a vývojového prostředí.
* Pokud už máte sadu QDK nainstalovanou, zkontrolujte, že je [aktualizovaná na nejnovější verzi](xref:microsoft.quantum.update)


## <a name="in-this-tutorial-youll-learn-how-to"></a>V tomto kurzu se naučíte:

> [!div class="checklist"]
> * Definování operací s více operačními operacemi v Q#
> * Volání Q# operací přímo z příkazového řádku nebo pomocí klasického hostitelského programu
> * Simulace operace s příchodem z přidělení qubit na výstup měření
> * Sledujte, jak se v průběhu operace vyvíjí simulovaný wavefunction systému

Běh programu pro práci s více operačními systémy od Microsoftu se bude obvykle skládat ze dvou částí:
1. Samotný program, který je implementován pomocí programovacího jazyka pro práci po sobě Q# a následně vyvolán ke spuštění na počítači s více operačními systémy nebo simulátoru provozu. Ty se skládají z 
    - Q# operace: podrutiny fungující na registrech v případě nečinnosti 
    - Q# Functions: klasické podrutiny používané v rámci algoritmu doby.
2. Vstupní bod, který slouží k volání programu pro práci s poli, a určení cílového počítače, na kterém by měl být spuštěn.
    To lze provést přímo z příkazového řádku nebo prostřednictvím hostitelského programu napsaného v klasickém programovacím jazyce, jako je Python nebo C#.
    Tento kurz obsahuje pokyny pro libovolný způsob, kterým dáváte přednost.

## <a name="allocate-qubits-and-define-quantum-operations"></a>Přidělte qubits a definujte operace

První část tohoto kurzu se skládá z definice Q# operace `Perform3qubitQFT` , která provádí funkci Fourierova transformace na třech qubits. 

Kromě toho budeme pomocí této [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) funkce sledovat, jak se simulované wavefunctiony našeho tří systémů qubit v rámci operace vyvíjely.

Prvním krokem je vytvoření Q# projektu a souboru.
Postup pro tyto kroky závisí na prostředí, které použijete pro volání programu, a podrobnosti najdete v příslušných [pokynech k instalaci](xref:microsoft.quantum.install).

Provedeme vás jednotlivými komponentami souboru, ale kód je také k dispozici jako úplný blok níže.

### <a name="namespaces-to-access-other-no-locq-operations"></a>Obory názvů pro přístup k jiným Q# operacím
V souboru nejdřív nadefinujeme obor názvů, ke `NamespaceQFT` kterému bude mít kompilátor přistup.
Abychom mohli využít stávající Q# operace, otevřou se příslušné `Microsoft.Quantum.<>` obory názvů.

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a>Definovat operace s argumenty a vrácení
Dále definujeme `Perform3qubitQFT` operaci:

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

V současné době operace přebírá žádné argumenty a nevrátí nic---v tomto případě zapíšeme, že vrátí `Unit` objekt, který je podobají `void` v jazyce C# nebo prázdná řazená kolekce členů `Tuple[()]` v Pythonu.
Později ji Upravme, aby vracela pole výsledků měření. v tomto okamžiku se `Unit` nahradí `Result[]` . 

### <a name="allocate-qubits-with-using"></a>Přidělit qubits pomocí `using`
V rámci naší Q# operace nejprve přidělíme registraci tří qubits pomocí `using` příkazu:

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

V `using` případě se qubits automaticky přiřazují ve stavu $ \ket {0} $. Můžete to ověřit pomocí [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) a [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , který vypíše řetězec a aktuální stav systému do konzoly.

> [!NOTE]
> `Message(<string>)`Funkce a `DumpMachine()` (v [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) uvedeném pořadí) se tisknou přímo do konzoly. Stejně jako u reálných výpočetních Q# stavů neumožňuje přímý přístup ke qubit státům.
> `DumpMachine`Když ale vytisknete aktuální stav cílového počítače, může poskytnout cenné informace pro ladění a učení při použití ve spojení s simulátorem úplného stavu.


### <a name="applying-single-qubit-and-controlled-gates"></a>Použití jednoduchých qubit a řízených bran

V dalším kroku použijeme brány, které tvoří samotnou operaci.
Q# již obsahuje mnoho základních bran jako operací v [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) oboru názvů a nejsou to žádné výjimky. 

V rámci Q# operace budou příkazy, které vyvolává volání, samozřejmě spouštěny v sekvenčním pořadí.
Proto první brána, která se má použít, je [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) na první qubit:

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

Pro použití operace na konkrétní qubit z registru (tj. jedna `Qubit` z pole `Qubit[]` ) používáme zápis standardního indexu.
Proto použití pro na [`H`](xref:microsoft.quantum.intrinsic.h) první qubit našeho registru má `qs` podobu:

```qsharp
            H(qs[0]);
```

Kromě použití `H` brány (Hadamard) pro jednotlivé qubits se okruh QFT skládá hlavně z řízených [`R1`](xref:microsoft.quantum.intrinsic.r1) otočení.
`R1(θ, <qubit>)`Operace obecně ponechá součást $ \ket {0} $ qubit beze změny a při použití rotace $e ^ {i\theta} $ na součást $ \ket {1} $.

#### <a name="controlled-operations"></a>Řízené operace

Q# způsobuje velmi snadné spuštění operace na jednom nebo několika qubits ovládacích prvků.
Obecně jsme zavedli pouze volání s `Controlled` a argumenty operace se mění jako:

 `Op(<normal args>)` $ \to $ `Controlled Op([<control qubits>], (<normal args>))` .

Všimněte si, že qubits ovládacího prvku musí být poskytnut jako pole, i když se jedná o jediný qubit.

Po `H` , uvidíme, že další brány jsou `R1` brány působící na první qubit (a řízená druhou/třetí):

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

Budeme je volat pomocí

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

Všimněte si, že používáme [`PI()`](xref:microsoft.quantum.math.pi) funkci z [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) oboru názvů k definování otočení v souvislosti s pí radiány.
Kromě toho jsme vydělíme `Double` (např. `2.0` ), protože rozdělením pomocí celého čísla `2` by vyvolalo chybu typu. 

> [!TIP]
> `R1(π/2)` a `R1(π/4)` jsou ekvivalentem `S` operací a `T` (také v `Microsoft.Quantum.Intrinsic` ).


Po použití relevantních `H` operací a řízených otočení na druhý a třetí qubits:

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

[`SWAP`](xref:microsoft.quantum.intrinsic.swap)pro dokončení okruhu musíme použít jenom bránu:

```qsharp
            SWAP(qs[2], qs[0]);
```

To je nezbytné vzhledem k tomu, že povaha Fourierova transformace vrací qubits v obráceném pořadí, takže swapy umožňují bezproblémovou integraci subrutiny do větších algoritmů.

Proto jsme dokončili vytváření qubit operací na úrovni, které je potřeba transformovat, do naší Q# operace:

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

Nemůžeme ho ale ještě zavolat na den.
Naše qubits byly ve stavu $ \ket {0} $, když je jsme jim přiřadili a podobně jako v životě Q# byste měli mít stejné možnosti jako v případě, že jsme je našli (nebo lepší!).

### <a name="deallocate-qubits"></a>Zrušit přidělení qubits

Znovu se zavoláme [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , aby se zobrazil stav po operaci, a nakonec se v [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) registru qubit resetuje náš qubits na $ \ket {0} $, než se dokončí operace:

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

Vyžadování, aby všechny navrácené qubits byly explicitně nastavené na $ \ket {0} $, je základní funkcí Q# nástroje, protože umožňuje jiným operacím přesně znát jejich stav, když začnou používat stejné qubits (prostředek omezených).
Navíc to zaručuje, že nebudou entangled s žádným jiným qubits v systému.
Pokud se resetování neprovede na konci `using` bloku přidělení, bude vyvolána Běhová chyba.

Úplný Q# soubor by teď měl vypadat takto:

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


Po Q# dokončení souboru a operace je náš program pro práci s více operačními systémem připravený k volání a simulaci.

## <a name="run-the-program"></a>Spuštění programu

Po definování naší Q# operace v `.qs` souboru teď musíme tuto operaci zavolat a sledovat všechna vrácená klasická data.
V současné době se nevrátí nic (odvolání této operace definované výše `Unit` ), ale když později tuto operaci upravíte, Q# aby vracela pole výsledků měření ( `Result[]` ), budeme na to řešit.

I když Q# je program všudypřítomný napříč prostředími používanými k jeho volání, tak se takovým způsobem bude samozřejmě lišit. Stačí postupovat podle pokynů na kartě, která odpovídá vaší instalaci: pracuje z Q# aplikace nebo používá hostitelský program v Pythonu nebo C#.

#### <a name="command-prompt"></a>[Příkazový řádek](#tab/tabid-cmdline)

Spuštění Q# programu z příkazového řádku vyžaduje pouze malou změnu Q# souboru.

Jednoduše přidejte `@EntryPoint()` na řádek před definici operace:

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

Chcete-li spustit program, otevřete terminál ve složce projektu a zadejte

```dotnetcli
dotnet run
```

Po dokončení byste měli vidět `Message` `DumpMachine` výstupy a níže vytisknuté ve vaší konzole.


#### <a name="python"></a>[Python](#tab/tabid-python)

Vytvořit soubor hostitele Pythonu: `host.py` .

Hostitelský soubor je vytvořen takto: 
1. Nejdřív naimportujeme `qsharp` modul, který registruje zavaděč modulu pro Q# interoperabilitu. 
    To umožňuje Q# obory názvů (například `NamespaceQFT` jsme definovali v našem Q# souboru), aby se zobrazily jako moduly Pythonu, ze kterých můžeme importovat Q# operace.
2. Pak importujte Q# operace, které v tomto případě přímo vyvoláme--- `Perform3qubitQFT` .
    Je potřeba importovat vstupní bod do Q# programu (tj. _nejedná_ se o operace `H` , jako `R1` jsou a, které jsou volány jinými Q# operacemi, ale nikdy klasickým hostitelem).
3. Při simulaci Q# operací nebo funkcí použijte formulář `<Q#callable>.simulate(<args>)` ke spuštění na `QuantumSimulator()` cílovém počítači. 

> [!NOTE]
> Pokud jsme chtěli volat operaci na jiném počítači, například `ResourceEstimator()` prostě, můžeme použít `<Q#callable>.estimate_resources(<args>)` .
> Obecně platí, Q# že operace se nezávislá na počítače, na kterých jsou spuštěny, ale některé funkce se `DumpMachine` mohou chovat jinak.

4. Po vykonání simulace vrátí volání operace hodnoty, jak je definováno v Q# souboru.
    V případě, že se teď nic nevrátí, ale později se vám zobrazí příklad přiřazení a zpracování těchto hodnot.
    Díky tomu, že jsou výsledná data v našich rukou i zcela klasická, můžeme s ní dělat jakékoli věci.

Úplný `host.py` soubor by měl být následující:

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

Spusťte soubor Pythonu a vytisknutý ve vaší konzole byste měli vidět `Message` `DumpMachine` níže uvedené výstupy a. 


#### <a name="c"></a>[C#](#tab/tabid-csharp)

Podle stejných pokynů jako v [instalační příručce](xref:microsoft.quantum.install.cs)vytvořte soubor hostitele v jazyce C# a přejmenujte ho na `host.cs` .

Hostitel C# má čtyři části:
1. Vytvoření kvantového simulátoru.
    V následujícím kódu je to proměnná `qsim` .
2. Vypočítá všechny argumenty vyžadované pro kvantový algoritmus.
    V tomto příkladu nejsou žádné.
3. Spusťte kvantový algoritmus. 
    Každá Q# operace vygeneruje třídu jazyka C# se stejným názvem. 
    Tato třída má `Run` metodu, která spouští operaci **asynchronně**.
    Spuštění je asynchronní, protože jeho spuštění na skutečném hardwaru bude asynchronní. 
    Vzhledem k tomu `Run` , že metoda je asynchronní, zavoláme `Wait()` metodu. Tato operace zablokuje spuštění, dokud se úloha nedokončí a výsledek vrátí synchronně. 
4. Zpracování vráceného výsledku operace.
    V současné době operace nevrátí žádnou hodnotu.


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
Spusťte aplikaci a váš výstup by měl odpovídat následujícímu.
Program se ukončí po stisknutí klávesy.
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

Při volání na plný stav simulátoru `DumpMachine()` poskytuje tyto několik reprezentace wavefunction stavu. Možné stavy $n $-qubit systému můžou být reprezentovány pomocí výpočetních stavů $2 ^ n $, každý s odpovídajícím komplexním koeficientem (jenom amplitudou a fází).
Výpočetní stavy odpovídají všem možným binárním řetězcům s délkou $n $---to znamená všechny možné kombinace qubit stavů $ \ket {0} $ a $ \ket {1} $, kde každá binární číslice odpovídá individuálnímu qubit.

První řádek poskytuje komentář s ID odpovídající qubits v jejich významném pořadí.
Qubit je `2` "nejvýznamnější" jednoduše znamená, že v binárním vyjádření základního stavu Vector $ \ket{i} $ je stav qubit `2` odpovídá číslici vlevo. Například $ \ket {6} = \ket {110} $ zahrnuje qubits `2` a v $ `1` \ket {1} $ a qubit `0` v $ \ket {0} $.


Ostatní řádky popisují amplitudu pravděpodobnosti měření vektoru stavu $ \ket{i} $ v kartézském a polárních formátech.
Podrobnosti o prvním řádku našeho vstupního stavu $ \ket {000} $:
* **`|0>:`** Tento řádek odpovídá `0` výpočetnímu stavu (vzhledem k tomu, že naše počáteční přidělení stavu bylo $ \ket {000} $, očekávalo se, že by to byl jediný stav s amplitudou pravděpodobnosti v tomto okamžiku).
* **`1.000000 +  0.000000 i`**: amplituda pravděpodobnosti ve formátu kartézském.
* **` == `**: `equal` znaménko odděluje rovnocenné reprezentace.
* **`********************`**: Grafická reprezentace velikosti, počet `*` je úměrný pravděpodobnosti měření tohoto vektoru stavu. 
* **`[ 1.000000 ]`**: číselná hodnota velikosti
* **`    ---`**: Grafická reprezentace fáze amplitudy.
* **`[ 0.0000 rad ]`**: číselná hodnota fáze (v radiánech).

Velikost i fáze se zobrazí s grafickým znázorněním. Reprezentace velikosti je jednoduchá: zobrazuje pruh `*` a čím vyšší je pravděpodobnost, tím větší bude pruh. Pro fázi si přečtěte téma [testování a ladění: funkce výpisu](xref:microsoft.quantum.guide.testingdebugging#dump-functions) pro možné reprezentace symbolů na základě rozsahů úhlů.


Vytištěný výstup tedy ilustruje, že naše naprogramované brány transformují náš stav z

$ $ \ket{\psi} \_ {Initial} = \ket {000} $ $

na 

$ $ \begin{align} \ket{\psi} \_ {Final} &= \frac {1} {\sqrt {8} } \left (\ket {000} + \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} \right) \\ \\ &= \frac {1} {\sqrt{2 ^ n} \sum \ket{j} \_ {j = 0} ^ {2 ^ n-1} \end{align}, $ $

což je přesné chování 3-qubit Fourierova transformace. 

Pokud jste zajímái o tom, jak jsou ovlivněny další vstupní stavy, doporučujeme, abyste se přehráli s použitím operací qubit před transformací.

## <a name="adding-measurements"></a>Přidávání měření

Bohužel, na základě základu nečinnosti oznamujeme, že skutečný systém pro plnění do něj nemůže mít takovou `DumpMachine` funkci. Místo toho je nutné extrahovat informace prostřednictvím měření, což obecně nestačí pouze v plném rozsahu, ale může také významně změnit samotný systém.
Existuje mnoho druhů měření doby plnění, ale u jednotlivých qubits se zaměříme na nejvíc základní: měření při projekci.
Po měření v daném základu (např. výpočetního základu $ \{ \ket {0} , \ket {1} \} $) se stav qubit prochází na základě stavu, který se měří,---proto zničení všech dvou míst.

K implementaci měření v rámci Q# programu používáme `M` operaci (z `Microsoft.Quantum.Intrinsic` ), která vrací `Result` typ.

Nejdřív jsme tuto operaci změnili `Perform3QubitQFT` tak, aby vracela pole výsledků měření, `Result[]` a ne `Unit` .

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a>Definovat a inicializovat `Result[]` pole

Před tím, než se přidělí qubits (tj. před `using` příkazem), deklarujeme a navážeme toto pole length-3 (jedna `Result` pro každý qubit): 

```qsharp
        mutable resultArray = new Result[3];
```

`mutable`Klíčové slovo `resultArray` , které předkládá, umožňuje, aby proměnná byla později převázána v kódu---například při přidávání výsledků měření.

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a>Provádění měření ve `for` smyčce a přidání výsledků do pole

Po operacích Fourierova transformace uvnitř `using` bloku vložte následující kód:

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
[`IndexRange`](xref:microsoft.quantum.arrays.indexrange)Funkce volaná na poli (například naše pole qubits, `qs` ) vrací rozsah v rámci indexů pole. Tady ho v naší smyčce používáme `for` k sekvenčnímu měření jednotlivých qubit pomocí `M(qs[i])` příkazu.
Každý měřený `Result` typ (buď `Zero` nebo `One` ) je poté přidán do odpovídající pozice indexu v `resultArray` příkazu s příkazem Update-a-Reassign.

> [!NOTE]
> Syntaxe tohoto příkazu je jedinečná pro Q# , ale odpovídá podobné změně přiřazení proměnné `resultArray[i] <- M(qs[i])` v jiných jazycích, například F # a R.

Klíčové slovo `set` se vždycky používá k opětovnému přiřazení proměnných vázaných pomocí `mutable` .

#### <a name="return-resultarray"></a>Vrátit `resultArray`

Se všemi třemi qubitsy změřenými a výsledky přidanými do je `resultArray` bezpečné resetování a navrácení qubits jako dříve.
Po `using` zavření bloku vložte

```qsharp
        return resultArray;
```
nakonec vrátí výstup naší operace. 

### <a name="understanding-the-effects-of-measurement"></a>Porozumění efektům měření

Pojďme změnit umístění našich `DumpMachine` funkcí na výstup stavu před a po měření.
Kód poslední operace by měl vypadat takto: 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

Pokud pracujete z příkazového řádku, vrácené pole bude na konci běhu jednoduše zobrazeno přímo na konzoli.
V opačném případě aktualizujte hostitelský program pro zpracování vráceného pole.

#### <a name="command-prompt"></a>[Příkazový řádek](#tab/tabid-cmdline)

Aby bylo možné porozumět vrácenému poli, které bude vytištěno v konzole, můžeme do souboru přidat další `Message` do Q# příkazu těsně před `return` příkazem:

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

Spusťte projekt a váš výstup by měl vypadat nějak takto:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[Python](#tab/tabid-python)

Aktualizujte program Pythonu následujícím způsobem:

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

Spusťte soubor a váš výstup by měl vypadat nějak takto:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

Teď, když naše operace vrací výsledek, nahraďte volání metody `Wait()` načtením `Result` Vlastnosti. Tím se stále doplní stejný synchronicity, který jsme projednali dříve, a můžeme přímo navazovat tuto hodnotu na proměnnou `measurementResult` .

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

Spusťte projekt a váš výstup by měl vypadat nějak takto:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

Tento výstup znázorňuje několik různých věcí:
1. Porovnání vráceného výsledku s předměřením `DumpMachine` jasně neilustruje QFTou polohu nad základními stavy. _not_
    Měření vrací jenom jeden základní stav s pravděpodobností určenou amplitudou tohoto stavu v wavefunction systému.
2. Od po měření `DumpMachine` vidíte, že měření _mění_ samotný stav a prochází je od počátečního umístění v rámci jednotlivých stavů do jediného základního stavu, který odpovídá měřené hodnotě.

Pokud bychom tuto operaci opakovali mnohokrát, poznamenali jsme, že se výsledky začnou začínat, aby se zobrazila rovnoměrně vážená pozice stavu post-QFT. Výsledkem je náhodný výsledek u každého snímku.
_Nicméně_, kromě neefektivních a stále dokonalé, by však došlo pouze k reprodukování relativních amplitud základních stavů, nikoli mezi jejich relativními fázemi.
V tomto příkladu se nejedná o problém, ale v případě složitějšího vstupu do QFT než $ \ket $ by se zobrazily relativní fáze {000} .

#### <a name="partial-measurements"></a>Částečná měření 
Chcete-li prozkoumat, jak měření pouze některých qubits registru může ovlivnit stav systému, zkuste přidat následující dovnitř `for` smyčky za řádek měření:
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

Všimněte si, že pro přístup k této `IntAsString` funkci budete muset přidat 
```qsharp
    open Microsoft.Quantum.Convert;
```
se zbytkem příkazů oboru názvů `open` .

Ve výsledném výstupu se při měření jednotlivých qubit zobrazí postupná projekce na podprostory.


## <a name="use-the-no-locq-libraries"></a>Použití Q# knihoven
Jak jsme se už zmínili v úvodu, mnoho z Q# nich je ve skutečnosti, že vám umožní abstrakci vypořádat se s jednotlivými qubits.
V případě, že chcete vyvíjet plně škálovatelné programy pro práci s více procesory, je třeba se obávat, zda `H` operace proběhne před nebo po určitém otočení, pouze zpomalení. 

Q#Knihovny obsahují operaci [QFT](xref:microsoft.quantum.canon.qft) , kterou můžete jednoduše použít a použít pro libovolný počet qubits.
Pokud to chcete vyzkoušet, definujte novou operaci v Q# souboru, která má stejný obsah `Perform3QubitQFT` , ale s vše od prvního `H` až po `SWAP` nahrazené dvěma jednoduchými řádky:
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
První řádek jednoduše vytvoří [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) výraz přiděleného pole qubits, `qs` což je to, co operace [QFT](xref:microsoft.quantum.canon.qft) přijímá jako argument.
To odpovídá pořadí indexu qubits v registru.

Chcete-li mít přístup k těmto operacím, přidejte `open` příkazy pro příslušné obory názvů na začátku Q# souboru:
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

Nyní upravte hostitelský program tak, aby volal název vaší nové operace (např. `PerformIntrinsicQFT` ), a pojmenujte ho whirl.

Chcete-li zjistit skutečnou výhodu použití Q# operací knihovny, změňte počet qubits na jinou než `3` :
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
Proto můžete použít správný QFT pro libovolný počet qubits, aniž byste se museli starat o práci s novými `H` operacemi a rotacemi na jednotlivých qubit.

Všimněte si, že simulátor provozu má exponenciálně víc času na spuštění, protože narostete počet qubits---přesně, proč se podíváme na skutečný hardware.













