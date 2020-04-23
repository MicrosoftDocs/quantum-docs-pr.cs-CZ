---
title: Testování a ladění programů Q#
description: Naučte se používat testy částí, fakta a kontrolní výrazy a výpis funkce pro testování a ladění kvantové programy.
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030578"
---
# <a name="testing-and-debugging"></a>Testování a ladění

Stejně jako u klasického programování, je nezbytné, aby bylo možné zkontrolovat, že kvantové programy působí tak, jak bylo zamýšleno, a aby bylo možné diagnostikovat kvantový program, který je nesprávný.
V této části se zabýváme nástroji, které nabízí Q# pro testování a ladění kvantových programů.

## <a name="unit-tests"></a>Jednotkové testy

Jedním z běžných přístupů k testování klasických programů je psaní malých programů nazývaných *testy částí,* které spouštějí kód v knihovně a porovnávají jeho výstup s očekávaným výstupem.
Například, můžeme chtít zajistit, aby `Square(2)` vrací `4`, protože víme, a *priori,* že $ 2 ^ 2 = 4 $.

Q# podporuje vytváření testů částí pro kvantové programy, které mohou být provedeny jako testy v rámci testování jednotky [xUnit.](https://xunit.github.io/)

### <a name="creating-a-test-project"></a>Vytvoření testovacího projektu

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Otevřete Visual Studio 2019. Přejděte `File` do nabídky `New`  >  `Project...`a vyberte .
V pravém horním rohu `Q#`vyhledejte a `Q# Test Project` vyberte šablonu.

#### <a name="command-line--visual-studio-code"></a>[Příkazový řádek / Visual Studio Code](#tab/tabid-vscode)

Na oblíbeném příkazovém řádku spusťte následující příkaz:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Váš nový projekt bude `Tests.qs`mít jeden soubor , který poskytuje vhodné místo pro definování nových testů jednotek Q#.
Zpočátku tento soubor obsahuje `AllocateQubit` jeden test vzorkovací jednotky, který zkontroluje,{0}zda nově přidělený qubit je ve stavu $\ket $ a vytiskne zprávu:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:new: Všechny Q# operace nebo funkce, `Unit` která `Unit` má argument typu a `@Test("...")` vrátí lze označit jako test jednotky prostřednictvím atributu. Argument k tomuto `"QuantumSimulator"` atributu výše určuje cíl, na kterém je test proveden. Jeden test lze provést na více cílů. Přidejte například `@Test("ResourcesEstimator")` atribut `AllocateQubit`výše . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Uložte soubor a proveďte všechny testy. Nyní by měl y být dva testy částí, jeden kde Je spuštěn AllocateQubit na QuantumSimulator a jeden, kde je spuštěn v ResourceEstimator. 

Kompilátor Q# rozpozná předdefinované cíle "QuantumSimulator", "ToffoliSimulator" a "ResourcesEstimator" jako platné cíle provádění pro testy částí. Je také možné zadat libovolný plně kvalifikovaný název pro definování cíle vlastního spuštění. 

### <a name="running-q-unit-tests"></a>Spuštění testů jednotek Q#

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Jako jednorázové nastavení řešení přejděte do `Test` nabídky `Test Settings`  >  `Default Processor Architecture`  >  `X64`a vyberte .

> [!TIP]
> Výchozí nastavení architektury procesoru pro Visual Studio`.suo`je uloženo v souboru možností řešení ( ) pro každé řešení.
> Pokud odstraníte tento soubor, budete `X64` muset znovu vybrat jako architekturu procesoru.

Sestavte projekt, `Test` přejděte `Windows`  >  `Test Explorer`do nabídky a vyberte . `AllocateQubit`v seznamu testů ve `Not Run Tests` skupině. Vyberte `Run All` nebo spusťte tento individuální test, a to by mělo projít!

#### <a name="command-line--visual-studio-code"></a>[Příkazový řádek / Visual Studio Code](#tab/tabid-vscode)

Chcete-li spustit testy, přejděte do `Tests.csproj`složky projektu (složka, která obsahuje ) a spusťte příkaz:

```bash
$ dotnet restore
$ dotnet test
```

Měli byste získat výstup podobný následujícímu:

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

Jednotkové testy lze filtrovat podle jejich názvu a/nebo cíle spuštění:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

Vnitřní funkce <xref:microsoft.quantum.intrinsic.message> má typ `(String -> Unit)` a umožňuje vytváření diagnostických zpráv.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Po provedení testu v Průzkumníkovi testů a kliknutí na test se zobrazí panel s informacemi o spuštění testu: Předané/neúspěšné stav, uplynulý čas a odkaz "Výstup". Pokud kliknete na odkaz "Výstup", testovací výstup se otevře v novém okně.

![testovací výstup](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Příkazový řádek / Visual Studio Code](#tab/tabid-vscode)

Stav průchodu/selhání pro každý test je `dotnet test`vytištěn do konzoly společností .
Pro selhání testů jsou výstupy také vytištěny do konzoly, aby pomohly diagnostikovat selhání.

***

## <a name="facts-and-assertions"></a>Fakta a tvrzení

Vzhledem k tomu, že funkce v Q# nemají žádné _logické_ vedlejší účinky, `()` žádné jiné _druhy_ účinků provádění funkce, jejíž výstupní typ je prázdná řazená kolekce členů, nelze nikdy pozorovat z programu Q#.
To znamená, že cílový počítač může zvolit `()` neprovádět žádnou funkci, která se vrátí se zárukou, že toto opomenutí nezmění chování žádného následujícího kódu Q#.
Díky funkcím `()` vracejícím se `Unit`(tj. ) jako užitečný nástroj pro vkládání kontrolních výrazů a logiky ladění do programů Q#. 

Podívejme se na jednoduchý příklad:

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

Zde klíčové `fail` slovo označuje, že by nemělo pokračovat výpočtu, což vyvolává výjimku v cílovém počítači se spuštěným programem Q#.
Podle definice selhání tohoto druhu nelze pozorovat z q#, jako žádný další `fail` Q # kód je spuštěn po dosažení příkazu.
Pokud tedy budeme pokračovat po `PositivityFact`výzvě k , můžeme si být jisti, že jeho vstup byl pozitivní.

Všimněte si, že můžeme `PositivityFact` implementovat stejné chování jako pomocí [`Fact`](xref:microsoft.quantum.diagnostics.fact) funkce z oboru <xref:microsoft.quantum.diagnostics> názvů:

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

*Kontrolní výrazy*, na druhé straně se používají podobně jako fakta, ale může být závislá na stavu cílového stroje. Odpovídajícím způsobem jsou definovány jako operace, zatímco fakta jsou definována jako funkce (jak je uvedeno výše).
Chcete-li pochopit rozdíl, zvažte následující použití skutečnosti v rámci tvrzení:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

Zde používáme operaci <xref:microsoft.quantum.environment.getqubitsavailabletouse> k vrácení počtu qubitů, které jsou k dispozici pro použití.
Vzhledem k tomu, že to jasně závisí na globálním `AssertQubitsAreAvailable` stavu programu a jeho provádění prostředí, naše definice musí být operace stejně.
Tento globální stav však můžeme použít `Bool` k zadání `Fact` jednoduché hodnoty jako vstupu do funkce.

V návaznosti na tyto myšlenky, [předehra](xref:microsoft.quantum.libraries.standard.prelude) nabízí dvě obzvláště užitečná tvrzení, <xref:microsoft.quantum.intrinsic.assert> a <xref:microsoft.quantum.intrinsic.assertprob> to jak modelované jako operace na `()`. Tato tvrzení každý vzít Operátor Pauli popisující konkrétní měření zájmu, kvantový registr, na kterém má být provedeno měření, a hypotetický výsledek.
Na cílových strojích, které pracují simulací, nejsme vázáni [neklonující teorém](https://en.wikipedia.org/wiki/No-cloning_theorem), a může provádět taková měření bez narušení registru předán a tato tvrzení.
Simulátor pak může, podobně `PositivityFact` jako výše uvedené funkce, přerušit výpočty, pokud hypotetický výsledek by nebyl dodržen v praxi:

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

Na fyzickém kvantovém hardwaru, kde neklonující teorém zabraňuje zkoumání kvantového stavu, `Assert` se operace a `AssertProb` jednoduše vrátí `()` bez jiného účinku.

Obor <xref:microsoft.quantum.diagnostics> názvů poskytuje několik dalších funkcí rodiny, `Assert` které nám umožňují kontrolovat pokročilejší podmínky. 

## <a name="dump-functions"></a>Funkce výpisu

Chcete-li pomoci při <xref:microsoft.quantum.diagnostics> řešení potíží s kvantovými programy, obor názvů nabízí <xref:microsoft.quantum.diagnostics.dumpmachine> <xref:microsoft.quantum.diagnostics.dumpregister>dvě funkce, které lze vykládat do souboru aktuální stav cílového počítače: a . Generovaný výstup každého z nich závisí na cílovém stroji.

### <a name="dumpmachine"></a>DumpMachine

Full-state kvantový simulátor distribuovaný jako součást Quantum Development Kit zapíše do souboru [vlnovou funkci](https://en.wikipedia.org/wiki/Wave_function) celého kvantového systému, jako jednorozměrné pole komplexních čísel, ve kterém každý prvek představuje amplitudu pravděpodobnosti měření výpočtového základu stavu $\ket{n}$, kde $\ket{n} = \ket{b_{n-1}... b_1b_0}$ za bity $\{b_i\}$. Například na počítači s přidělenými pouze dvěma qubity a v kvantovém stavu $${1}\begin{align}{2}\ket{\psi} = \frac {\sqrt } \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ volání <xref:microsoft.quantum.diagnostics.dumpmachine> generuje tento výstup:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

První řádek poskytuje komentář s ID odpovídajícíqubity v jejich významné pořadí.
Zbývající řádky popisují amplitudu pravděpodobnosti měření vektoru stavu základu $\ket{n}$ v kartézském i polárním formátu. Podrobně pro první řádek:

* **`∣0❭:`** tento řádek odpovídá `0` stavu výpočtového základu
* **`0.707107 +  0.000000 i`**: amplituda pravděpodobnosti v kartézské majedře.
* **` == `**: `equal` znaménko sereperates obě ekvivalentní reprezentace.
* **`**********  `**: Grafické znázornění velikosti, `*` počet je úměrný pravděpodobnosti měření tohoto vektoru stavu.
* **`[ 0.500000 ]`**: číselná hodnota velikosti
* **`    ---`**: Grafické znázornění fáze amplitudy (viz níže).
* **`[ 0.0000 rad ]`**: číselná hodnota fáze (v radiánech).

Velikost i fáze jsou zobrazeny s grafickým znázorněním. Velikost reprezentace je rovný-vpřed: ukazuje `*`bar , tím větší je pravděpodobnost, že větší bar bude. Pro fázi zobrazujeme následující symboly, které představují úhel založený na rozsahu:

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

Následující příklady `DumpMachine` ukazují některé běžné stavy:

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
  > Id qubit je přiřazen za běhu a není nutně zarovnán s pořadím, ve kterém byl qubit přidělen, nebo jeho pozice v registru qubit.


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Můžete zjistit qubit id v sadě Visual Studio vložením zarážku v kódu a kontrolou hodnoty qubit proměnné, například:
  > 
  > ![zobrazit qubit id v sadě Visual Studio](~/media/qubit_id.png)
  >
  > qubit s `0` indexem na `register2` `3`má id= `1` , qubit`2`s indexem má id= .

#### <a name="command-line--visual-studio-code"></a>[Příkazový řádek / Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Můžete zjistit qubit id pomocí <xref:microsoft.quantum.intrinsic.message> funkce a předávání qubit proměnné ve zprávě, například:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > které by mohly tento výstup generovat:
  >```
  > 0=q:3; 1=q:2
  >```
  > což `0` znamená, že qubit `register2` s indexem na má`3` `1` id=`2`, qubit s indexem má id= .


***

<xref:microsoft.quantum.diagnostics.dumpmachine>je součástí <xref:microsoft.quantum.diagnostics> oboru názvů, takže chcete-li jej `open` použít, musíte přidat příkaz:

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

<xref:microsoft.quantum.diagnostics.dumpregister>funguje <xref:microsoft.quantum.diagnostics.dumpmachine>jako , s výjimkou to také trvá řadu qubits omezit množství informací pouze na to, které jsou relevantní pro odpovídající qubity.

Stejně <xref:microsoft.quantum.diagnostics.dumpmachine>jako u , <xref:microsoft.quantum.diagnostics.dumpregister> informace generované závisí na cílovém stroji. Pro full-state kvantový simulátor zapíše do souboru vlnovou funkci až do globální fáze kvantového subsystému generovaného poskytnutými qubity ve stejném formátu jako <xref:microsoft.quantum.diagnostics.dumpmachine>.  Například vezměte znovu stroj s pouze dvěma qubity přidělenými a v kvantovém stavu $${1}\begin{align}{2}\ket{\psi} ={00} \frac{2} {\sqrt } \ket - \frac{(1 + i)} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ volající <xref:microsoft.quantum.diagnostics.dumpregister> generuje `qubit[0]` tento výstup:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

a <xref:microsoft.quantum.diagnostics.dumpregister> volání `qubit[1]` generuje tento výstup:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Obecně platí, že stav registru, který je zapletený s jiným registrem je smíšený stav, nikoli čistý stav. V tomto <xref:microsoft.quantum.diagnostics.dumpregister> případě výstupy následující zprávu:

```
Qubits provided (0;) are entangled with some other qubit.
```

Následující příklad ukazuje, jak můžete <xref:microsoft.quantum.diagnostics.dumpregister> <xref:microsoft.quantum.diagnostics.dumpmachine> použít jak a v kódu Q#:

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

`Assert` Nad a `Dump` funkce a operace Q# podporuje podmnožinu standardních možností ladění Visual Studio: nastavení [zarážky řádku](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [krokování kódu pomocí F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) a kontrola hodnoty klasické [proměnné](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) jsou všechny možné během provádění kódu na simulátoru.

Ladění v kódu sady Visual Studio využívá možnosti ladění poskytované c# pro rozšíření kódu Visual Studio powered by OmniSharp a vyžaduje instalaci [nejnovější verze](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp). 
