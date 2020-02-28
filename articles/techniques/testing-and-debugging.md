---
title: 'Testování a ladění programů Q #'
description: Naučte se používat testy jednotek, fakta a kontrolní výrazy a funkce výpisu paměti pro testování a ladění programů v počtu procesorů.
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3df8df8defabcc9cc87d59f543f425c882b001e0
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907677"
---
# <a name="testing-and-debugging"></a>Testování a ladění

Stejně jako v případě klasického programování je nutné mít na úmysl kontrolu nad tím, že se programy budou chovat podle účelu a že je možné diagnostiku nesprávného programu.
V této části se zaměříme na nástroje, které Q # nabízí pro testování a ladění programů v oblasti.

## <a name="unit-tests"></a>Testy jednotek

Jedním z běžných způsobů testování klasických programů je psaní malých programů s názvem *testy jednotek* , které spouštějí kód v knihovně, a porovnání jeho výstupu s očekávaným výstupem.
Můžeme třeba zajistit, aby `Square(2)` vracela `4`, protože víme předem, že *je* to $2 ^ 2 = $4.

Q # podporuje vytváření testů jednotek pro programy na více procesorech a to, které mohou být provedeny jako testy v rámci testovacího rozhraní [xUnit](https://xunit.github.io/) jednotek.

### <a name="creating-a-test-project"></a>Vytvoření testovacího projektu

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Otevřete Visual Studio 2019. Přejděte do nabídky `File` a vyberte `New` > `Project...`.
V pravém horním rohu vyhledejte `Q#`a vyberte šablonu `Q# Test Project`.

#### <a name="command-line--visual-studio-code"></a>[Příkazový řádek / Visual Studio Code](#tab/tabid-vscode)

Z oblíbeného příkazového řádku spusťte následující příkaz:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Nový projekt bude mít jeden soubor `Tests.qs`, který poskytuje vhodné místo pro definování nových testů jednotek Q #.
Zpočátku tento soubor obsahuje jeden vzorový test jednotek `AllocateQubit`, který kontroluje, zda je nově přidělená qubit ve stavu $ \ket{0}$ a vytiskne zprávu:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

: New: operace Q # nebo funkce, která přebírá argument typu `Unit` a vrací `Unit` může být označena jako test jednotky prostřednictvím atributu `@Test("...")`. Argument tohoto atributu `"QuantumSimulator"` výše určuje cíl, na kterém je test spuštěn. Jeden test může být proveden na více cílech. Přidejte například atribut `@Test("ResourcesEstimator")` výše `AllocateQubit`. 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Uložte soubor a proveďte všechny testy. Nyní by měly být dvě testy jednotek, jedna kde AllocateQubit je spuštěna na QuantumSimulator a druhá, kde se spustí v ResourceEstimator. 

Kompilátor Q # rozpoznává předdefinované cíle "QuantumSimulator", "ToffoliSimulator" a "ResourcesEstimator" jako platné cíle provádění pro testování částí. Je také možné zadat libovolný plně kvalifikovaný název pro definování vlastního cíle provádění. 

### <a name="running-q-unit-tests"></a>Spouštění testů jednotek Q #

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Jako jednorázové nastavení pro každé řešení přejděte do nabídky `Test` a vyberte `Test Settings` > `Default Processor Architecture` > `X64`.

> [!TIP]
> Výchozí nastavení architektury procesoru pro Visual Studio je uloženo v souboru možností řešení (`.suo`) pro každé řešení.
> Pokud tento soubor odstraníte, budete muset jako architekturu procesoru vybrat `X64`.

Sestavte projekt, přejděte do nabídky `Test` a vyberte `Windows` > `Test Explorer`. `AllocateQubit` se zobrazí v seznamu testů ve `Not Run Tests` skupině. Vyberte `Run All` nebo spusťte tento jednotlivý test a měl by být úspěch.

#### <a name="command-line--visual-studio-code"></a>[Příkazový řádek / Visual Studio Code](#tab/tabid-vscode)

Chcete-li spustit testy, přejděte do složky projektu (složka obsahující `Tests.csproj`) a spusťte příkaz:

```bash
$ dotnet restore
$ dotnet test
```

Mělo by se zobrazit výstup podobný následujícímu:

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

Testy jednotek lze filtrovat podle jejich názvu nebo cíle provádění:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

Vnitřní funkce <xref:microsoft.quantum.intrinsic.message> je typu `(String -> Unit)` a umožňuje vytváření diagnostických zpráv.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Po spuštění testu v Průzkumníku testů a kliknutí na test se zobrazí panel s informacemi o spuštění testu: stav úspěch/selhání, uplynulý čas a "výstup". Pokud kliknete na odkaz "výstup", výstup testu se otevře v novém okně.

![Výstup testu](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Příkazový řádek / Visual Studio Code](#tab/tabid-vscode)

Stav úspěch/selhání každého testu je vytištěn do konzoly `dotnet test`.
V případě neúspěšných testů jsou výstupy také vytištěny do konzoly nástroje, což vám umožní diagnostikovat selhání.

***

## <a name="facts-and-assertions"></a>Fakta a kontrolní výrazy

Vzhledem k tomu, že funkce v Q # nemají žádné _logické_ vedlejší účinky, jakýmkoli _jiným druhem_ efektů provádění funkce, jejíž výstupní typ je prázdná řazená kolekce členů, `()` v rámci programu Q # nikdy nemusejí být zjištěny.
To znamená, že cílový počítač se může rozhodnout, že nespustí žádnou funkci, která vrátí `()` s jistotou, že toto opomenutí neupraví chování žádného následujícího kódu Q #.
Díky tomu funkce vracející `()` (tj. `Unit`) užitečný nástroj pro vkládání kontrolních výrazů a logiku ladění do programů Q #. 

Pojďme si vzít v úvahu jednoduchý příklad:

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

Zde `fail` klíčové slovo indikuje, že výpočet by neměl pokračovat, vyvolání výjimky v cílovém počítači, na kterém běží program Q #.
Podle definice nemůže být selhání tohoto druhu zjištěno v rámci Q #, protože po dosažení `fail`ho příkazu není spuštěn žádný další kód Q #.
Proto, pokud budeme pokračovat po volání `PositivityFact`, můžeme mít jistotu, že jeho vstup byl kladný.

Všimněte si, že je možné implementovat stejné chování jako `PositivityFact` pomocí funkce [`Fact`](xref:microsoft.quantum.diagnostics.fact) z oboru názvů <xref:microsoft.quantum.diagnostics>:

```qsharp
    Fact(value <= 0, "Expected a positive number.");
```

*Kontrolní výrazy*jsou na druhé straně používány podobně jako fakta, ale mohou být závislé na stavu cílového počítače. Odpovídajícím způsobem jsou definovány jako operace, zatímco fakta jsou definována jako funkce (jak je uvedeno výše).
Pro pochopení rozlišení zvažte následující použití faktu v rámci kontrolního výrazu:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

V tomto příkladu používáme operaci <xref:microsoft.quantum.environment.getqubitsavailabletouse> k vrácení počtu dostupných qubits k použití.
Vzhledem k tomu, že to jasně závisí na globálním stavu programu a jeho prováděcím prostředí, musí být naše definice `AssertQubitsAreAvailable` také operace.
Tento globální stav však můžeme použít k získání jednoduché `Bool`é hodnoty jako vstupu do funkce `Fact`.

[Předehru](xref:microsoft.quantum.libraries.standard.prelude) na těchto nápadech nabízí dva obzvláště užitečné kontrolní výrazy, <xref:microsoft.quantum.intrinsic.assert> a <xref:microsoft.quantum.intrinsic.assertprob> jak modelovat jako operace na `()`. Tyto kontrolní výrazy přebírají operátor Pauli, který popisuje konkrétní měření zájmu, registrující hodnoty, na kterých se má provést měření, a hypotetický výsledek.
V cílových počítačích, které pracují s simulací, nebudeme vázáni pomocí [věta bez klonování](https://en.wikipedia.org/wiki/No-cloning_theorem)a může provádět taková měření, aniž by došlo k narušení registru předaného do takových kontrolních výrazů.
Simulátor pak může být podobný funkci `PositivityFact` výše, přerušit výpočet, pokud by se hypotetický výsledek neosvědčil v praxi:

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

U fyzických stavových procesorů, kde věta bez klonování brání prověřování stavu nečinnosti, operace `Assert` a `AssertProb` jednoduše vrátí `()` bez dalšího účinku.

Obor názvů <xref:microsoft.quantum.diagnostics> poskytuje několik dalších funkcí řady `Assert`, které nám umožňují kontrolovat pokročilejší podmínky. 

## <a name="dump-functions"></a>Funkce výpisu paměti

Pro pomoc při řešení potíží s programy, <xref:microsoft.quantum.diagnostics> obor názvů nabízí dvě funkce, které mohou vypsat do souboru aktuální stav cílového počítače: <xref:microsoft.quantum.diagnostics.dumpmachine> a <xref:microsoft.quantum.diagnostics.dumpregister>. Vygenerovaný výstup každého z nich závisí na cílovém počítači.

### <a name="dumpmachine"></a>DumpMachine

Plný stav simulátoru, který je distribuován jako součást vývojářské sady pro plnění, zapisuje do souboru [funkci Wave](https://en.wikipedia.org/wiki/Wave_function) celého systému pro základní hodnoty, jako jednorozměrné pole komplexních čísel, kde každý prvek představuje amplitudu pravděpodobnosti měření rozdílového stavu výpočtu $ \ket{n} $, kde $ \ket{n} = \ket{B_ {n-1}... b_1b_0} $ pro BITS $\{b_i\}$. Například na počítači, který má přiděleno pouze dvě qubits a ve stavu nestavování $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ Call <xref:microsoft.quantum.diagnostics.dumpmachine> generuje tento výstup:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

První řádek poskytuje komentář s ID odpovídající qubits v jejich významném pořadí.
Ostatní řádky popisují amplitudu pravděpodobnosti měření vektoru stavu $ \ket{n} $ v kartézském a polárních formátech. Podrobně pro první řádek:

* **`∣0❭:`** tento řádek odpovídá průběžnému stavu `0` výpočtu.
* **`0.707107 +  0.000000 i`** : amplituda pravděpodobnosti ve formátu kartézském.
* **` == `** : znaménko `equal` se bude rozkládat se stejnými reprezentacemi.
* **`**********  `** : grafická reprezentace velikosti, počet `*` je úměrný pravděpodobnosti měření tohoto vektoru stavu.
* **`[ 0.500000 ]`** : číselná hodnota velikosti
* **`    ---`** : grafická reprezentace fáze amplitudy (viz níže).
* **`[ 0.0000 rad ]`** : číselná hodnota fáze (v radiánech).

Velikost i fáze se zobrazí s grafickým znázorněním. Reprezentace velikosti je přímá – předána: zobrazuje pruh `*`, tím větší je pravděpodobnost, že se další pruh zvětší. Pro tuto fázi zobrazíme následující symboly, které reprezentují úhel na základě rozsahů:

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

Následující příklady ukazují `DumpMachine` v některých běžných stavech:

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > ID qubit se přiřadí za běhu a není nutně zarovnané na pořadí, ve kterém byla qubit přidělena nebo jeho pozice v rámci registru qubit.


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > ID qubit v aplikaci Visual Studio můžete zjistit tak, že do kódu zadáte zarážku a zkontrolujete hodnotu proměnné qubit, například:
  > 
  > ![Zobrazit ID qubit v aplikaci Visual Studio](~/media/qubit_id.png)
  >
  > qubit s index `0` v `register2` má ID =`3`, qubit s index `1` má ID =`2`.

#### <a name="command-line--visual-studio-code"></a>[Příkazový řádek / Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > ID qubit můžete zjistit pomocí funkce <xref:microsoft.quantum.intrinsic.message> a předáním proměnné qubit ve zprávě, například:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > který může vygenerovat tento výstup:
  >```
  > 0=q:3; 1=q:2
  >```
  > To znamená, že qubit s indexem `0` v `register2` má ID =`3`, qubit s index `1` má ID =`2`.


***

<xref:microsoft.quantum.diagnostics.dumpmachine> je součástí oboru názvů <xref:microsoft.quantum.diagnostics>, takže pokud ho chcete použít, musíte přidat příkaz `open`:

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a>DumpRegister

<xref:microsoft.quantum.diagnostics.dumpregister> funguje jako <xref:microsoft.quantum.diagnostics.dumpmachine>s tím rozdílem, že také převezme pole qubits k omezení množství informací pouze na odpovídající qubits.

Stejně jako u <xref:microsoft.quantum.diagnostics.dumpmachine>jsou informace vygenerované <xref:microsoft.quantum.diagnostics.dumpregister> závislé na cílovém počítači. Pro plný stav simulátoru se zapisuje do souboru, ve kterém je funkce Wave v globální fázi podsystému, vygenerované zadaným qubits ve stejném formátu jako <xref:microsoft.quantum.diagnostics.dumpmachine>.  Například znovu proveďte počítač se dvěma přidělenými qubits a ve stavu stavového pole $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ PI/4} ((\frac{1}{\sqrt{2}} \ket{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}), \end{align} $ $ volá <xref:microsoft.quantum.diagnostics.dumpregister> pro `qubit[0]` vygeneruje tento výstup. :

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

a volání <xref:microsoft.quantum.diagnostics.dumpregister> pro `qubit[1]` vygeneruje tento výstup:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Obecně platí, že stav registru, který je entangled s jiným registrem, je smíšeným stavem, nikoli čistým stavem. V tomto případě <xref:microsoft.quantum.diagnostics.dumpregister> výstupem následující zprávu:

```
Qubits provided (0;) are entangled with some other qubit.
```

Následující příklad ukazuje, jak můžete použít jak <xref:microsoft.quantum.diagnostics.dumpregister>, tak <xref:microsoft.quantum.diagnostics.dumpmachine> ve vašem kódu Q #:

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a>Ladění

Na začátku `Assert` a `Dump` funkce a operace Q # podporuje podmnožinu standardních možností ladění sady Visual Studio: [nastavení zarážek řádků](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [krokování kódu pomocí nástroje F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) a [Kontrola hodnot klasických proměnných](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) je všechno možné během provádění kódu v simulátoru.

Ladění v Visual Studio Code využívá možnosti ladění poskytované rozšířením C# pro Visual Studio Code, které používá OmniSharp a vyžaduje instalaci [nejnovější verze](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp). 
