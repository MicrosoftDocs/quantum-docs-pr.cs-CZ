---
title: Zkoumání provázání s využitím Q#
description: Naučte se psát kvantové programy v jazyce Q#. Vývoj aplikace demonstrující Bellovy stavy pomocí nástroje Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 10/07/2019
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 7836e39227fa2282c6e2faa039f6e625103d5403
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426846"
---
# <a name="tutorial-explore-entanglement-with-q"></a>Kurz: Zkoumání provázání s využitím Q\#

V tomto kurzu vám ukážeme, jak v jazyce Q# napsat program, který manipuluje s qubity, měří je a demonstruje efekty superpozice a provázání.
Tento dokument vás provede instalací sady QDK, sestavením programu a spuštěním programu na kvantovém simulátoru.  

Vytvoříme aplikaci nazvanou Bell, která demonstruje kvantové provázání.
Název Bell odkazuje na Bellovy stavy, což jsou specifické kvantové stavy 2 qubitů používané k demonstraci nejjednodušších příkladů superpozice a provázání.

## <a name="pre-requisites"></a>Požadavky

Chcete-li se pustit do kódování, nejprve proveďte tyto kroky: 

* [Instalace](xref:microsoft.quantum.install) vývojové sady s použitím preferovaného jazykového a vývojového prostředí
* Pokud už máte sadu QDK nainstalovanou, zkontrolujte, že je [aktualizovaná na nejnovější verzi](xref:microsoft.quantum.update)

Pokud se chcete jen seznámit se základy, můžete si článek přečíst i bez instalace sady QDK. Získáte tak přehled o programovacím jazyku Q# a základních koncepcích kvantových výpočtů.

## <a name="demonstrating-qubit-behavior-with-q"></a>Demonstrace chování qubitů pomocí Q#

Připomeňme si naši jednoduchou definici [qubitu](xref:microsoft.quantum.overview.understanding).  Zatímco klasické bity obsahují jednu binární hodnotu (tj. 0 nebo 1), qubit se může současně nacházet v **superpozici** stavů 0 a 1.  Qubit si můžete představit jako směr v prostoru (označuje se také jako vektor).  Qubit může být natočený do libovolného směru. Dva **klasické stavy** odpovídají dvěma směrům. Představují 100% šanci na změření 0 a 100% šanci na změření 1.  Tuto reprezentaci je možné formálněji vizualizovat [Blochovou koulí](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).


Akce měření poskytuje binární výsledek a mění stav qubitu. Měřením získáme binární hodnotu, buď 0, nebo 1.  V důsledku měření přejde qubit ze superpozice (libovolného směru) do jednoho z klasických stavů.  Všechna následná opakovaná měření bez provedení dalších operací už budou poskytovat shodný binární výsledek.  

Několik qubitů může být také **provázáno**. Když změříme jeden provázaný qubit, změní se tím naše znalost stavu ostatních qubitů.

Nyní jsme připraveni ukázat, jak se toto chování vyjadřuje v jazyce Q#.  Začneme s nejjednodušším možným programem a sestavíme ho tak, abychom demonstrovali kvantovou superpozici a provázání.

## <a name="setup"></a>Nastavení

Aplikace vyvinuté pomocí nástroje Microsoft Quantum Development Kit se skládají ze dvou částí:

1. Jeden nebo více kvantových algoritmů, implementovaných v kvantovém programovacím jazyce Q#.
1. Hostitelský program implementovaný v programovacím jazyce jako Python nebo C#, který slouží jako hlavní vstupní bod a vyvolává kvantové algoritmy jako operace Q#.

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Vyberte umístění aplikace.

1. Vytvořte soubor s názvem `Bell.qs`. Tento soubor bude obsahovat váš kód Q#.

1. Vytvořte soubor s názvem `host.py`. Tento soubor bude obsahovat váš hostitelský kód v Pythonu.

#### <a name="c-command-line"></a>[Příkazový řádek C#](#tab/tabid-csharp)

1. Vytvoření nového projektu Q#

    ```bash
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    Měli byste vidět soubor `.csproj`, soubor Q# s názvem `Operations.qs` a soubor hostitelského programu s názvem `Driver.cs`.

1. Přejmenování souboru Q#

    ```bash
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. Vytvoření nového projektu

   * Otevřete sadu Visual Studio.
   * V nabídce **Soubor** vyberte **Nový** -> **Projekt...** .
   * V průzkumníku šablon projektu zadejte do vyhledávacího pole `Q#` a vyberte šablonu `Q# Application`.
   * Dejte projektu název `Bell`.

1. Přejmenování souboru Q#

   * Přejděte na **Průzkumníka řešení**.
   * Klikněte pravým tlačítkem na soubor `Operations.qs`.
   * Přejmenujte ho na `Bell.qs`.

* * *

## <a name="write-a-q-operation"></a>Napište operaci Q#

Naším cílem je připravit dva qubity v určitém kvantovém stavu a demonstrovat tak, jak v Q# pracovat s qubity, měnit jejich stav a využívat efekty superpozice a provázání. Program sestavíme krok za krokem a předvedeme si stavy, operace a měření spojené s qubity.

**Přehled:**  V prvním kódu níže si ukážeme, jak v jazyce Q# pracovat s qubity.  Zavedeme dvě operace `M` a `X`, které mění stav qubitu. 

V tomto fragmentu kódu je použita operace `Set`, která přijímá jako parametr qubit a další parametr `desired` označující stav, do kterého chceme qubit převést.  Operace `Set` provádí měření qubitu pomocí operace `M`.  V Q# vrací měření qubitu vždy buď `Zero`, nebo `One`.  Pokud měření vrátí hodnotu, která není rovna požadované hodnotě, operace Set qubit „překlopí“. To znamená, že provede operaci `X`, která změní stav qubit na nový stav, ve kterém jsou pravděpodobnosti změření `Zero` a `One` převrácené.  Pro předvedení efektu operace `Set` je pak přidána operace `TestBellState`.  Tato operace jako vstup přebírá `Zero` nebo `One`, několikrát s tímto vstupem zavolá operaci `Set` a spočítá, kolikrát byla z měření qubitu vrácena hodnota `Zero` a kolikrát `One`. Samozřejmě v této první simulaci operace `TestBellState` očekáváme, že všechna měření qubitu nastaveného pomocí vstupního parametru `Zero` vrátí hodnotu `Zero` a všechna měření qubitu nastaveného pomocí parametru `One` vrátí `One`.  Dále do operace `TestBellState` přidáme kód pro demonstraci superpozice a provázání.


### <a name="q-operation-code"></a>Kód operace Q#

1. Obsah souboru Bell.qs nahraďte následujícím kódem:

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    Teď můžeme zavolat tuto operaci, aby nastavila qubit do klasického stavu a vrátila buď hodnotu `Zero` ve 100 % případů, nebo hodnotu `One` ve 100 % případů.  `Zero` a `One` jsou konstanty, které představují pouze dva možné výsledky měření stavu qubitu.

    Operace `Set` měří qubit.
    Pokud je qubit ve stavu, který chceme, `Set` ho nechá být, v opačném případě provedením operace `X` změní stav qubitu na požadovaný stav.

### <a name="about-q-operations"></a>Operace v jazyce Q#

Operace Q # je vlastně kvantový podprogram. To znamená, že se jedná o volanou rutinu, která obsahuje kvantové operace.

Argumenty operace jsou zadány jako řazené kolekce členů v závorkách.

Návratový typ operace je určen za dvojtečkou. V našem případě operace `Set` nic nevrací, takže je označena jako vracející `Unit`. Toto je v jazyce Q# ekvivalentem pojmu `unit` v F#, což je hrubá analogie `void` v C# a prázdné řazené kolekci členů v Pythonu (`Tuple[()]`).

V naší první operaci Q# jsme použili dvě kvantové operace:

* Operaci [M](xref:microsoft.quantum.intrinsic.m), která měří stav qubitu.
* Operaci [X](xref:microsoft.quantum.intrinsic.x), která převrací stav qubitu.

Kvantová operace mění stav qubitu. Někdy se mluví o kvantových hradlech místo kvantových operacích, je totiž možná i analogie s klasickými logickými hradly. Tento koncept pochází z raných dob kvantových výpočtů, kdy byly algoritmy jen teoretické konstrukce a vizualizovaly se ve formě schémat odpovídacích obvodovým schématům klasických počítačů.

### <a name="add-q-test-code"></a>Přidání testovacího kódu Q#

1. Přidejte do souboru `Bell.qs` následující operaci, do oboru názvů za konec operace `Set`:

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    Tato operace (`TestBellState`) se zopakuje v `count` iteracích, v každé nastaví zadanou hodnotu qubitu `initial` a pak změří výsledek (`M`). Shromáždí statistiku o počtu naměřených nul a jedniček a vrátí je volajícímu. Provede ale ještě jednu důležitou operaci. Před návratem resetuje qubit do známého stavu (`Zero`), aby ostatní mohli tento qubit použít ve známém stavu. To je provedeno příkazem `using`.

### <a name="about-variables-in-q"></a>Proměnné v jazyce Q#

Ve výchozím nastavení jsou proměnné v Q# neměnné; po jejich svázání už je nelze změnit. Klíčové slovo `let` slouží k označení vazby neměnné proměnné. Argumenty operace jsou vždycky neměnné.

Pokud potřebujete proměnnou, jejíž hodnotu je možné změnit, například `numOnes` v našem příkladu, můžete proměnnou deklarovat pomocí klíčového slova `mutable`. Hodnotu proměnlivé proměnné lze změnit pomocí příkazu `set`.

V obou případech je typ proměnné odvozen kompilátorem. Q# nevyžaduje pro proměnné žádné specifikace typu.

### <a name="about-using-statements-in-q"></a>Příkazy `using` v Q#

Příkaz `using` je také jedinečný pro jazyk Q#. Slouží k přidělení qubitů pro použití v bloku kódu. V Q# se všechny qubity dynamicky přidělují a uvolňují, protože se nejedná o pevné prostředky, které jsou k dispozici pro celou dobu běhu složitého algoritmu. Příkaz `using` přidělí sadu qubitů na začátku a uvolní je na konci bloku.

## <a name="create-the-host-application-code"></a>Vytvořte kód hostitelské aplikace

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Otevřete soubor `host.py` a přidejte následující kód:

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

1. Obsah souboru `Driver.cs` nahraďte následujícím kódem:

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a>Kód hostitelské aplikace

#### <a name="python"></a>[Python](#tab/tabid-python)

Hostitelská aplikace v jazyce Python má tři části:

* Vypočítá všechny argumenty vyžadované pro kvantový algoritmus. V příkladu je proměnná `count` nastavena pevně na 1000 a počáteční hodnota qubitu je `initial`.
* Spusťte kvantový algoritmus zavoláním metody `simulate()` importované operace Q#.
* Zpracujte výsledek operace. V příkladu bude `res` obsahovat výsledek operace. Zde je výsledkem řazená kolekce členů – počet nul (`num_zeros`) a počet jedniček (`num_ones`) změřených simulátorem. Z řazené kolekce členů získáme dvě pole a vytiskneme výsledky.

#### <a name="c"></a>[C#](#tab/tabid-csharp)

Hostitelská aplikace C# má čtyři části:

* Vytvoření kvantového simulátoru. V tomto příkladu je simulátorem `qsim`.
* Vypočítá všechny argumenty vyžadované pro kvantový algoritmus. V příkladu je proměnná `count` nastavena pevně na 1000 a počáteční hodnota qubitu je `initial`.
* Spusťte kvantový algoritmus. Každá operace Q# vygeneruje třídu C# se stejným názvem. Tato třída má metodu `Run`, která operaci **asynchronně** provede. Spuštění je asynchronní, protože asynchronní bude i spuštění na skutečném hardwaru. Vzhledem k tomu, že metoda `Run` je asynchronní, načteme vlastnost `Result`; tím se běh zastaví do doby, dokud se úloha nedokončí a nevrátí výsledek synchronně.
* Zpracujte výsledek operace. V příkladu bude `res` obsahovat výsledek operace. Zde je výsledkem řazená kolekce členů – počet nul (`numZeros`) a počet jedniček (`numOnes`) změřených simulátorem. To se vrátí v C# jako ValueTuple. Z řazené kolekce členů získáme dvě pole, vytiskneme výsledky a počkáme na stisk klávesy.

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a>Sestavení a spuštění

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Zadejte v okně terminálu následující příkaz:

    ```
    python host.py
    ```

    Tento příkaz spustí hostitelskou aplikaci, která provede simulaci operace Q#.

Výsledky by měly být:

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[Příkazový řádek / Visual Studio Code](#tab/tabid-csharp)

1. Spusťte v okně terminálu následující příkaz:

    ```bash
    dotnet run
    ```

    Tento příkaz automaticky stáhne všechny požadované balíčky, sestaví aplikaci a pak ji spustí na příkazovém řádku.

1. Případně můžete stisknutím **F1** otevřít paletu příkazů a vybrat **Ladění: Spustit bez ladění.**
Může se zobrazit výzva k vytvoření nového souboru ``launch.json`` popisujícího spuštění programu.
Výchozí ``launch.json`` by měl dobře fungovat pro většinu aplikací.

Výsledky by měly být:

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. Stiskněte `F5` a váš program by měl sestavit a spustit!

Výsledky by měly být:

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

Program se ukončí po stisknutí klávesy.

* * *

## <a name="prepare-superposition"></a>Příprava superpozice

**Přehled** Nyní se podíváme na to, jak Q# vyjadřuje způsoby, jak uvést qubity do superpozice.  Připomeňme si, že stav qubitu může být superpozicí hodnot 0 a 1.  Dosáhneme toho operací `Hadamard`. Pokud je qubit v některém z klasických stavů (kdy měření vrátí vždy `Zero` nebo vždy `One`), pak operace `Hadamard` nebo `H` převede qubit do stavu, ve kterém měření vrátí v 50 % případů `Zero` a v 50 % případů `One`.  Můžete si to představit tak, že qubit je uprostřed mezi `Zero` a `One`.  Když teď budeme simulovat operaci `TestBellState`, uvidíme, že jednotlivá měření vrátí přibližně stejný počet hodnot `Zero` a `One`.  

Nejdřív zkusíme qubit překlopit (pokud je qubit ve stavu `Zero`, překlopíme ho na `One` a naopak). Toho se dosáhne použitím operace `X` před změřením v operaci `TestBellState`:

```qsharp
X(qubit);
let res = M(qubit);
```

Nyní jsou výsledky (po stisknutí `F5`) obrácené:

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

Ovšem všechno, co jsme doposud viděli, je klasické. Pojďme se dostat ke kvantovým výsledkům. Stačí k tomu nahradit operaci `X` v předchozím běhu operací `H` (Hadamard). Místo úplného překlopení qubitu z 0 na 1 ho můžeme překlopit jen napůl. Změněné řádky v `TestBellState` teď vypadají takto:

```qsharp
H(qubit);
let res = M(qubit);
```

Teď už výsledky budou zajímavější:

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

Každým měřením požádáme o klasickou hodnotu, ale qubit je uprostřed mezi 0 a 1, takže (statisticky) dostaneme v polovině případů 0 a v polovině případů 1. To se označuje jako __superpozice__ a je to naše první seznámení s kvantovými stavy.

## <a name="prepare-entanglement"></a>Příprava provázání

**Přehled:**  Teď se podíváme na to, jak se v Q# vyjadřuje kvantové provázání qubitů.  Nejdřív uvedeme první qubit do počátečního stavu a pak ho pomocí operace `H` převedeme do superpozice.  Pak před změřením prvního qubitu použijeme novou operaci `CNOT`, což je zkratka pro Controlled-Not, kontrolovanou negaci.  Výsledkem provedení této operace na dvou qubitech je překlopení druhého qubitu, pokud je první ve stavu `One`.  Nyní máme dva provázané qubity.  Statistika prvního qubitu se nezměnila (stále šance 50-50, že měřením získáme `Zero` nebo `One`), ale když teď změříme stav druhého qubitu, bude __vždy__ stejný jako stav naměřený u toho prvního. Operace `CNOT` provázala oba qubity, takže cokoli se stane jednomu, stane se i druhému. Když pořadí měření otočíme (změříme nejprve druhý a pak první qubit), dostaneme úplně stejný výsledek. První měření bude náhodné, ale druhé bude přesně kopírovat výsledek toho prvního.

První věc, kterou je potřeba udělat, je přidělit v operaci `TestBellState` dva qubity místo jednoho:

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

To nám umožní přidat novou operaci (`CNOT`) před změřením (`M`) v operaci `TestBellState`:

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

Přidali jsme další operaci `Set` inicializující první qubit, abychom se ujistili, že je vždy v počátečním stavu `Zero`.

Stejně tak musíme resetovat druhý qubit, než ho na konci uvolníme.

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

Úplná rutina teď vypadá takto:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

Když ji spustíme, získáme přesně stejný výsledek 50-50, jako předtím. Co nás ale zajímá je způsob, jakým druhý qubit reaguje na první měřenou hodnotu. Tuto statistiku přidáme s novou verzí operace `TestBellState`:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

Nová návratová hodnota (`agree`) počítá případy, kdy se měření prvního qubitu shodovalo s měřením druhého qubitu. Také je potřeba odpovídajícím způsobem aktualizovat hostitelskou aplikaci:

#### <a name="python"></a>[Python](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

Po spuštění dostaneme moc zajímavý výsledek:

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

Jak jsme uvedli v přehledu, statistika prvního qubitu se nezměnila (stále šance 50:50, že získáme 0 nebo 1), ale teď když změříme stav druhého qubitu, bude __vždy__ stejný, jako změřený stav toho prvního, protože jsou provázané!

Blahopřejeme, napsali jste svůj první kvantový program!

## <a name="whats-next"></a>Co dále?

Kurz [Groverův vyhledávací algoritmus](xref:microsoft.quantum.quickstarts.search) vám ukáže, jak implementovat a spustit Groverovo vyhledávání, jeden z nejoblíbenějších kvantových výpočetních algoritmů, a nabízí dobrý příklad programu Q#, který se dá použít k řešení reálných problémů pomocí kvantových výpočtů.  

Dokument [Začínáme se sadou Quantum Development Kit](xref:microsoft.quantum.welcome) vám nabídne další způsoby, jak se seznámit s jazykem Q# a kvantovými programy.

