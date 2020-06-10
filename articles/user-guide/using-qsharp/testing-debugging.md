---
title: Testování a ladění
description: Naučte se používat testy jednotek, fakta a kontrolní výrazy a funkce výpisu paměti pro testování a ladění programů v počtu procesorů.
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
ms.openlocfilehash: dd6c7ae8a016423f26c37f3eedf0ae9c1d126b78
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630032"
---
# <a name="testing-and-debugging"></a>Testování a ladění

Stejně jako v případě klasického programování je nutné mít na úmysl kontrolu nad tím, že se programy budou chovat podle účelu a že je možné diagnostiku nesprávného programu.
V této části se zaměříme na nástroje, které Q # nabízí pro testování a ladění programů v oblasti.

## <a name="unit-tests"></a>Testování částí

Jedním z běžných způsobů testování klasických programů je psaní malých programů s názvem *testy jednotek* , které spouštějí kód v knihovně, a porovnání jeho výstupu s očekávaným výstupem.
Můžeme třeba zajistit, aby se `Square(2)` vracely informace, `4` protože víme *předem* , že $2 ^ 2 = $4.

Q # podporuje vytváření testů jednotek pro programy na více procesorech a to, které mohou být provedeny jako testy v rámci testovacího rozhraní [xUnit](https://xunit.github.io/) jednotek.

### <a name="creating-a-test-project"></a>Vytvoření testovacího projektu

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Otevřete Visual Studio 2019. Přejděte do `File` nabídky a vyberte `New`  >  `Project...` .
V pravém horním rohu vyhledejte `Q#` a vyberte `Q# Test Project` šablonu.

#### <a name="command-line--visual-studio-code"></a>[Příkazový řádek / Visual Studio Code](#tab/tabid-vscode)

Z oblíbeného příkazového řádku spusťte následující příkaz:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Nový projekt bude mít jeden soubor `Tests.qs` , který poskytuje pohodlný místo pro definování nových testů jednotek Q #.
Zpočátku tento soubor obsahuje jeden ukázkový test jednotky `AllocateQubit` , který kontroluje, zda je nově přidělená qubit ve stavu $ \ket {0} $ a vytiskne zprávu:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

: New: operace Q # nebo funkce, která přebírá argument typu `Unit` a vrácení, `Unit` může být označena jako test jednotky prostřednictvím `@Test("...")` atributu. Argument výše uvedeného atributu `"QuantumSimulator"` Určuje cíl, na kterém je test spuštěn. Jeden test může být proveden na více cílech. Přidejte například atribut `@Test("ResourcesEstimator")` výše `AllocateQubit` . 
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

Jako jednorázové nastavení jednotlivých řešení přejděte do `Test` nabídky a vyberte `Test Settings`  >  `Default Processor Architecture`  >  `X64` .

> [!TIP]
> Výchozí nastavení architektury procesoru pro Visual Studio je uloženo v souboru možností řešení ( `.suo` ) pro každé řešení.
> Pokud tento soubor odstraníte, budete ho muset `X64` znovu vybrat jako architekturu procesoru.

Sestavte projekt, přejděte do `Test` nabídky a vyberte `Windows`  >  `Test Explorer` . `AllocateQubit`zobrazí se v seznamu testů ve `Not Run Tests` skupině. Vyberte `Run All` nebo spusťte tento jednotlivý test a měl by být úspěch.

#### <a name="command-line--visual-studio-code"></a>[Příkazový řádek / Visual Studio Code](#tab/tabid-vscode)

Chcete-li spustit testy, přejděte do složky projektu (složka obsahující `Tests.csproj` ) a spusťte příkaz:

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

Vnitřní funkce <xref:microsoft.quantum.intrinsic.message> má typ `(String -> Unit)` a umožňuje vytváření diagnostických zpráv.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Po spuštění testu v Průzkumníku testů a kliknutí na test se zobrazí panel s informacemi o spuštění testu: stav úspěch/selhání, uplynulý čas a "výstup". Pokud kliknete na odkaz "výstup", výstup testu se otevře v novém okně.

![Výstup testu](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Příkazový řádek / Visual Studio Code](#tab/tabid-vscode)

Stav předání/selhání každého testu je vytištěn do konzoly nástrojem `dotnet test` .
V případě neúspěšných testů jsou výstupy také vytištěny do konzoly nástroje, což vám umožní diagnostikovat selhání.

***

## <a name="facts-and-assertions"></a>Fakta a kontrolní výrazy

Vzhledem k tomu, že funkce v Q # nemají žádné _logické_ vedlejší účinky, jakékoliv _jiné druhy_ účinků provádění funkce, jejíž výstupní typ je prázdná řazená kolekce členů, se v `()` programu Q # nikdy neprojeví.
To znamená, že cílový počítač se může rozhodnout, že nespustí žádnou funkci `()` , která se vrátí se zárukou, že toto opomenutí nebude upravovat chování žádného následujícího kódu Q #.
To umožňuje funkcím vracet `()` (tj. `Unit` ) užitečný nástroj pro vkládání kontrolních výrazů a logiku ladění do programů Q #. 

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

Zde klíčové slovo `fail` označuje, že výpočet by neměl pokračovat, vyvolání výjimky v cílovém počítači, na kterém je spuštěn program Q #.
Podle definice nemůže být selhání tohoto druhu zjištěno v rámci Q #, protože po dosažení příkazu není spuštěn žádný další kód Q # `fail` .
Proto, pokud budeme pokračovat po volání `PositivityFact` , můžeme si být jisti, že jeho vstup byl kladný.

Všimněte si, že můžeme implementovat stejné chování jako při `PositivityFact` použití [`Fact`](xref:microsoft.quantum.diagnostics.fact) funkce z <xref:microsoft.quantum.diagnostics> oboru názvů:

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

V tomto příkladu používáme operaci <xref:microsoft.quantum.environment.getqubitsavailabletouse> k vrácení počtu qubits dostupných k použití.
Vzhledem k tomu, že to jasně závisí na globálním stavu programu a jeho prováděcím prostředí, `AssertQubitsAreAvailable` musí být naše definice také operace.
Tento globální stav však můžeme použít k získání jednoduché `Bool` hodnoty jako vstupu do `Fact` funkce.

[Předehru](xref:microsoft.quantum.libraries.standard.prelude) na těchto nápadech nabízí dva obzvláště užitečné kontrolní výrazy, které se <xref:microsoft.quantum.intrinsic.assert> <xref:microsoft.quantum.intrinsic.assertprob> modelují jako operace na `()` . Tyto kontrolní výrazy přebírají operátor Pauli, který popisuje konkrétní měření zájmu, registrující hodnoty, na kterých se má provést měření, a hypotetický výsledek.
V cílových počítačích, které pracují s simulací, nebudeme vázáni pomocí [věta bez klonování](https://en.wikipedia.org/wiki/No-cloning_theorem)a může provádět taková měření, aniž by došlo k narušení registru předaného do takových kontrolních výrazů.
Simulátor pak může, podobně jako `PositivityFact` funkce výše, přerušit výpočet, pokud se hypotetický výsledek nepozoruje v praxi:

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

U fyzických stavových procesorů, kde věta bez klonování brání prověřování stavu `Assert` `AssertProb` nečinnosti, operace a se jednoduše vrátí `()` bez dalšího účinku.

<xref:microsoft.quantum.diagnostics>Obor názvů poskytuje několik dalších funkcí řady, `Assert` které nám umožňují kontrolovat pokročilejší podmínky. 

## <a name="dump-functions"></a>Funkce výpisu paměti

Pro pomoc při řešení potíží s programy, <xref:microsoft.quantum.diagnostics> obor názvů nabízí dvě funkce, které mohou vypsat do souboru aktuální stav cílového počítače: <xref:microsoft.quantum.diagnostics.dumpmachine> a <xref:microsoft.quantum.diagnostics.dumpregister> . Vygenerovaný výstup každého z nich závisí na cílovém počítači.

### <a name="dumpmachine"></a>DumpMachine

Plný stav simulátoru, který je distribuován jako součást vývojářské sady pro plnění, zapisuje do souboru [funkci Wave](https://en.wikipedia.org/wiki/Wave_function) celého systému pro základní hodnoty, jako jednorozměrné pole komplexních čísel, kde každý prvek představuje amplitudu pravděpodobnosti měření rozdílového stavu výpočtu $ \ket{n} $, kde $ \ket{n} = \ket{B_ {n-1}... b_1b_0} $ pro BITS $ \{ b_i \} $. Například na počítači, který má přiděleno pouze dvě qubits a ve stavu nestavení, je $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ Call <xref:microsoft.quantum.diagnostics.dumpmachine> generuje tento výstup:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

První řádek poskytuje komentář s ID odpovídající qubits v jejich významném pořadí.
Ostatní řádky popisují amplitudu pravděpodobnosti měření vektoru stavu $ \ket{n} $ v kartézském a polárních formátech. Podrobně pro první řádek:

* **`∣0❭:`** Tento řádek odpovídá `0` průběžnému stavu výpočtu.
* **`0.707107 +  0.000000 i`**: amplituda pravděpodobnosti ve formátu kartézském.
* **` == `**: `equal` znaménko odděluje rovnocenné reprezentace.
* **`**********  `**: Grafická reprezentace velikosti, počet `*` je úměrný pravděpodobnosti měření tohoto vektoru stavu.
* **`[ 0.500000 ]`**: číselná hodnota velikosti
* **`    ---`**: Grafická reprezentace fáze amplitudy (viz níže).
* **`[ 0.0000 rad ]`**: číselná hodnota fáze (v radiánech).

Velikost i fáze se zobrazí s grafickým znázorněním. Reprezentace velikosti je přímá – předána: zobrazuje pruh, což je `*` větší pravděpodobnost, po který se ovládací panel zvětšuje. Pro tuto fázi zobrazíme následující symboly, které reprezentují úhel na základě rozsahů:

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

Následující příklady znázorňují `DumpMachine` některé běžné stavy:

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
  > qubit s indexem `0` v `register2` má ID = `3` , qubit s indexem `1` má ID = `2` .

#### <a name="command-line--visual-studio-code"></a>[Příkazový řádek / Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > ID qubit můžete zjistit pomocí <xref:microsoft.quantum.intrinsic.message> funkce a předáním proměnné qubit ve zprávě, například:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > který může vygenerovat tento výstup:
  >```
  > 0=q:3; 1=q:2
  >```
  > To znamená, že qubit s indexem `0` na `register2` má ID = `3` , qubit s indexem `1` má ID = `2` .


***

<xref:microsoft.quantum.diagnostics.dumpmachine>je součástí <xref:microsoft.quantum.diagnostics> oboru názvů, takže aby ho bylo možné použít, je nutné přidat `open` příkaz:

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

<xref:microsoft.quantum.diagnostics.dumpregister>funguje podobně jako <xref:microsoft.quantum.diagnostics.dumpmachine> s tím rozdílem, že také přebírá pole qubits, které omezuje množství informací, které je relevantní pro odpovídající qubits.

Stejně jako u <xref:microsoft.quantum.diagnostics.dumpmachine> jsou informace vygenerované nástrojem <xref:microsoft.quantum.diagnostics.dumpregister> závislé na cílovém počítači. Pro plný stav simulátoru, který zapisuje do souboru, zapíše funkce Wave do globální fáze podsystému, který vygenerovala poskytnutá qubits ve stejném formátu jako <xref:microsoft.quantum.diagnostics.dumpmachine> .  Například znovu se přihlaste k počítači jenom se dvěma qubits přidělenými a ve stavu neobsazenosti $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ PI/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} \ket {2} {1} ) \otimes) {2} {0} , \end{align} $ $ volá se, <xref:microsoft.quantum.diagnostics.dumpregister> aby se `qubit[0]` vygeneroval tento výstup:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

a voláním metody <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[1]` generuje tento výstup:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Obecně platí, že stav registru, který je entangled s jiným registrem, je smíšeným stavem, nikoli čistým stavem. V tomto případě <xref:microsoft.quantum.diagnostics.dumpregister> výstup zobrazí následující zprávu:

```
Qubits provided (0;) are entangled with some other qubit.
```

Následující příklad ukazuje, jak můžete použít jak <xref:microsoft.quantum.diagnostics.dumpregister> a <xref:microsoft.quantum.diagnostics.dumpmachine> v kódu Q #:

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

V rámci `Assert` funkcí a `Dump` operací Q # podporuje podmnožinu standardních možností ladění sady Visual Studio: [nastavení zarážek řádků](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [krokování kódu pomocí nástroje F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) a [Kontrola hodnot klasických proměnných](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) je všechno možné při provádění kódu v simulátoru.

Ladění v Visual Studio Code využívá možnosti ladění poskytované v jazyce C# pro Visual Studio Code rozšíření využívající OmniSharp a vyžaduje instalaci [nejnovější verze](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp). 
