---
title: Prozkoumejte entanglement s Q#
description: Přečtěte si, jak napsat program pro vypisování do Q# . Vývoj aplikace demonstrující Bellovy stavy pomocí nástroje Quantum Development Kit (QDK)
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- Q#
- $$v
ms.openlocfilehash: d815a9a25b8ba5e9489b6d3d27fb0d64ab4aaa1d
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863444"
---
# <a name="tutorial-explore-entanglement-with-q"></a>Kurz: Zkoumání provázání s využitím Q\#

V tomto kurzu vám ukážeme, jak napsat Q# program, který pracuje s měřením qubits a ukazuje účinky nadpozice a entanglement.

Vytvoříme aplikaci nazvanou Bell, která demonstruje kvantové provázání.
Název Bell odkazuje na Bellovy stavy, což jsou specifické kvantové stavy 2 qubitů používané k demonstraci nejjednodušších příkladů superpozice a provázání.

## <a name="pre-requisites"></a>Požadavky

Chcete-li se pustit do kódování, nejprve proveďte tyto kroky: 

* [Nainstalujte](xref:microsoft.quantum.install) sadu pro vývoj pro práci s více jazyky pomocí vašeho preferovaného jazykového a vývojového prostředí.
* Pokud už máte sadu QDK nainstalovanou, zkontrolujte, že je [aktualizovaná na nejnovější verzi](xref:microsoft.quantum.update)

Můžete také postupovat spolu s mluveným komentářem bez instalace QDK, Projděte si přehledy Q# programovacího jazyka a první koncepty výpočetních prostředků.

## <a name="in-this-tutorial-youll-learn-how-to"></a>V tomto kurzu se naučíte:

> [!div class="checklist"]
> * Vytváření a kombinování operací v Q\#
> * Vytvořte operace pro vložení qubits do umístění, entangle a měření.
> * Demonstrujte neentanglementa za sebou za Q# běhu programu v simulátoru. 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a>Demonstrace chování qubit pomocí QDK

Zatímco klasické bity obsahují jednu binární hodnotu (tj. 0 nebo 1), [qubit](xref:microsoft.quantum.glossary#qubit) se může nacházet v **superpozici** stavů 0 a 1.  Koncepční, stav qubit lze představit jako směr v abstraktním prostoru (označuje se také jako vektor).  Stav qubit může být v libovolném z možných směrů. Dva **klasické stavy** odpovídají dvěma směrům. Představují 100% šanci na změření 0 a 100% šanci na změření 1.

Akce měření poskytuje binární výsledek a mění stav qubitu.
Měření vytvoří binární hodnotu, buď 0, nebo 1.  V důsledku měření přejde qubit ze superpozice (libovolného směru) do jednoho z klasických stavů.  Všechna následná opakovaná měření bez provedení dalších operací už budou poskytovat shodný binární výsledek.  

Několik qubitů může být také [**provázáno**](xref:microsoft.quantum.glossary#entanglement).  Když změříme jeden provázaný qubit, změní se tím naše znalost stavu ostatních qubitů.

Nyní jsme připraveni předvést, jak Q# Toto chování vyjadřuje.  Začneme s nejjednodušším možným programem a sestavíme ho tak, abychom demonstrovali kvantovou superpozici a provázání.

## <a name="creating-a-no-locq-project"></a>Vytvoření Q# projektu

První věc, kterou je potřeba udělat, je vytvoření nového Q# projektu. V tomto kurzu použijeme prostředí založené na [ Q# aplikacích s vs Code](xref:microsoft.quantum.install.standalone).

Chcete-li vytvořit nový projekt, v VS Code: 

1. Klikněte na **Zobrazení** -> **Paleta příkazů** a vyberte **Q#: Vytvořit nový projekt**.
2. Klikněte na **Samostatná konzolová aplikace**.
3. Přejděte do umístění, kam chcete projekt uložit, a klikněte na **Vytvořit projekt**.
4. Po úspěšném vytvoření projektu klikněte na **Otevřít nový projekt...** v pravém dolním rohu.

V tomto případě jsme volali projekt `Bell` . Tím se vytvoří dva soubory: `Bell.csproj` , soubor projektu a `Program.qs` Šablona aplikace, kterou použijeme Q# k zápisu naší aplikace. Obsah `Program.qs` by měl být:

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a>Zapsat aplikaci Q \#
 
Naším cílem je připravit dva qubitsy v určitém stavu, který ukazuje, jak pracovat na qubits s Q# cílem změnit svůj stav a Ukázat účinky nadpozice a entanglement. Za účelem zavedení qubitch států, operací a měření vám budeme sestavovat tuto část.

### <a name="initialize-qubit-using-measurement"></a>Inicializovat qubit pomocí měření

V prvním kódu níže vám ukážeme, jak pracovat s qubits v Q# .  Zavádíme dvě operace [`M`](xref:microsoft.quantum.intrinsic.m) a [`X`](xref:microsoft.quantum.intrinsic.x) transformují stav qubit. V tomto fragmentu kódu je použita operace `SetQubitState`, která přijímá jako parametr qubit a další parametr `desired` označující stav, do kterého chceme qubit převést.  Operace `SetQubitState` provádí měření qubitu pomocí operace `M`.  V Q# je měření qubit vždy vrací buď `Zero` nebo `One` .  Pokud měření vrátí hodnotu, která není rovna požadované hodnotě, "převrátí `SetQubitState` " qubit; to znamená, že spustí `X` operaci, která změní stav qubit na nový stav, ve kterém pravděpodobnost vracení měření vrací `Zero` a `One` jsou obráceny. Tímto způsobem `SetQubitState` vždy umístí cílový qubit do požadovaného stavu.

Nahraďte obsah `Program.qs` následujícím kódem:


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

Teď můžeme zavolat tuto operaci, aby nastavila qubit do klasického stavu a vrátila buď hodnotu `Zero` ve 100 % případů, nebo hodnotu `One` ve 100 % případů.
`Zero` a `One` jsou konstanty, které představují pouze dva možné výsledky měření stavu qubitu.

Operace `SetQubitState` měří qubit. Pokud je qubit ve stavu, který chceme, `SetQubitState` ho nechá být, v opačném případě provedením operace `X` změní stav qubitu na požadovaný stav.

#### <a name="about-no-locq-operations"></a>O Q# operacích

Q#Operace je podprogram nečinnosti. To znamená, že se jedná o volanou rutinu, která obsahuje volání jiných operací.

Argumenty operace jsou zadány jako řazené kolekce členů v závorkách.

Návratový typ operace je určen za dvojtečkou. V našem případě operace `SetQubitState` nic nevrací, takže je označena jako vracející `Unit`. Toto je Q# ekvivalent `unit` v F #, který je zhruba podobný `void` v jazyce C# a prázdná řazená kolekce členů ( `Tuple[()]` ) v Pythonu.

V první operaci jste použili dvě provozní operace Q# :

* [`M`](xref:microsoft.quantum.intrinsic.m)Operace, která měří stav qubit
* [`X`](xref:microsoft.quantum.intrinsic.x)Operace, která Překlopí stav qubit

Kvantová operace mění stav qubitu. Někdy se mluví o kvantových hradlech místo kvantových operacích, je totiž možná i analogie s klasickými logickými hradly. Tento koncept pochází z raných dob kvantových výpočtů, kdy byly algoritmy jen teoretické konstrukce a vizualizovaly se ve formě schémat odpovídacích obvodovým schématům klasických počítačů.

### <a name="counting-measurement-outcomes"></a>Počítání výsledků měření

Pro předvedení efektu operace `SetQubitState` je pak přidána operace `TestBellState`. Tato operace jako vstup přebírá `Zero` nebo `One`, několikrát s tímto vstupem zavolá operaci `SetQubitState` a spočítá, kolikrát byla z měření qubitu vrácena hodnota `Zero` a kolikrát `One`. Samozřejmě v této první simulaci operace `TestBellState` očekáváme, že všechna měření qubitu nastaveného pomocí vstupního parametru `Zero` vrátí hodnotu `Zero` a všechna měření qubitu nastaveného pomocí parametru `One` vrátí `One`. Dále přidáte kód k `TestBellState` předvedení entanglement a.

Přidejte do souboru `Program.qs` následující operaci, do oboru názvů za konec operace `SetQubitState`:

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
Všimněte si, že před `return` tiskem vysvětlující zprávy v konzole jsme přidali řádek s funkcí ( `Message` ) [Microsoft. prohlášeno. vnitřní. zpráva].

Tato operace (`TestBellState`) se zopakuje v `count` iteracích, v každé nastaví zadanou hodnotu qubitu `initial` a pak změří výsledek (`M`). Shromáždí statistiku o počtu naměřených nul a jedniček a vrátí je volajícímu. Provede ale ještě jednu důležitou operaci. Před návratem resetuje qubit do známého stavu (`Zero`), aby ostatní mohli tento qubit použít ve známém stavu. To je provedeno příkazem `using`.

#### <a name="about-variables-in-q"></a>O proměnných v Q\#

Ve výchozím nastavení proměnné v Q# jsou neměnné; jejich hodnota nesmí být po svázání změněna. Klíčové slovo `let` slouží k označení vazby neměnné proměnné. Argumenty operace jsou vždycky neměnné.

Pokud potřebujete proměnnou, jejíž hodnotu je možné změnit, například `numOnes` v našem příkladu, můžete proměnnou deklarovat pomocí klíčového slova `mutable`. Hodnotu proměnlivé proměnné lze změnit pomocí příkazu `setQubitState`.

V obou případech je typ proměnné odvozen kompilátorem. Q# pro proměnné nevyžadují žádné anotace typu.

#### <a name="about-using-statements-in-q"></a>O `using` příkazech v Q\#

`using`Příkaz je také speciální pro Q# . Slouží k přidělení qubitů pro použití v bloku kódu. V systému se Q# všechny qubits dynamicky přidělují a uvolňují, ale nejedná se o pevné prostředky, které jsou pro celou dobu života komplexního algoritmu. Příkaz `using` přidělí sadu qubitů na začátku a uvolní je na konci bloku.

## <a name="run-the-code-from-the-command-prompt"></a>Spuštění kódu z příkazového řádku

Aby bylo možné spustit kód, musíme zadat kompilátor, *který* se spustí při zadání `dotnet run` příkazu. To se provádí v případě jednoduché změny v Q# souboru přidáním řádku s `@EntryPoint()` přímo předcházejícím voláním: `TestBellState` operace v tomto případě. Úplný kód by měl být:

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

Aby bylo možné spustit program, musíme zadat `count` `initial` argumenty a z příkazového řádku. Vybereme například `count = 1000` a `initial = One` . Zadejte následující příkaz:

```dotnetcli
dotnet run --count 1000 --initial One
```

A měli byste sledovat následující výstup:

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

Pokud se o to pokusíte `initial = Zero` , měli byste sledovat:

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a>Příprava superpozice

Teď se podíváme na to, jak vyjadřuje způsob, jak Q# umístit qubits na pozici.  Připomeňme si, že stav qubitu může být superpozicí hodnot 0 a 1.  Dosáhneme toho operací `Hadamard`. Pokud je qubit v některém z klasických stavů (kdy měření vrátí vždy `Zero` nebo vždy `One`), pak operace `Hadamard` nebo `H` převede qubit do stavu, ve kterém měření vrátí v 50 % případů `Zero` a v 50 % případů `One`.  Můžete si to představit tak, že qubit je uprostřed mezi `Zero` a `One`.  Když teď budeme simulovat operaci `TestBellState`, uvidíme, že jednotlivá měření vrátí přibližně stejný počet hodnot `Zero` a `One`.  

### <a name="x-flips-qubit-state"></a>`X` Překlopí stav qubit.

Nejdřív zkusíme qubit překlopit (pokud je qubit ve stavu `Zero`, překlopíme ho na `One` a naopak). Toho se dosáhne použitím operace `X` před změřením v operaci `TestBellState`:

```qsharp
X(qubit);
let res = M(qubit);
```

Nyní jsou výsledky vráceny:

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

Teď se podíváme na vlastnosti pro qubits.

### <a name="h-prepares-superposition"></a>`H` připraví nadpozici

Stačí k tomu nahradit operaci `X` v předchozím běhu operací `H` (Hadamard). Místo úplného překlopení qubitu z 0 na 1 ho můžeme překlopit jen napůl. Změněné řádky v `TestBellState` teď vypadají takto:

```qsharp
H(qubit);
let res = M(qubit);
```

Teď už výsledky budou zajímavější:

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

Každým měřením požádáme o klasickou hodnotu, ale qubit je uprostřed mezi 0 a 1, takže (statisticky) dostaneme v polovině případů 0 a v polovině případů 1.
To se označuje jako **superpozice** a je to naše první seznámení s kvantovými stavy.

## <a name="prepare-entanglement"></a>Příprava provázání

Teď se podíváme na Q# to, jak vyjádřit možnosti entangle qubits.
Nejdřív uvedeme první qubit do počátečního stavu a pak ho pomocí operace `H` převedeme do superpozice.  Pak před měřením prvního qubit používáme novou operaci ( `CNOT` ), která se zaznamená pro kontrolu ne.  Výsledkem provedení této operace na dvou qubitech je překlopení druhého qubitu, pokud je první ve stavu `One`.  Nyní máme dva provázané qubity.  Statistika prvního qubitu se nezměnila (stále šance 50-50, že měřením získáme `Zero` nebo `One`), ale když teď změříme stav druhého qubitu, bude __vždy__ stejný jako stav naměřený u toho prvního. Operace `CNOT` provázala oba qubity, takže cokoli se stane jednomu, stane se i druhému. Když pořadí měření otočíme (změříme nejprve druhý a pak první qubit), dostaneme úplně stejný výsledek. První měření bude náhodné, ale druhé bude přesně kopírovat výsledek toho prvního.

První věc, kterou je potřeba udělat, je přidělit dvě qubits místo jedné v `TestBellState` :

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

To nám umožní přidat novou operaci (`CNOT`) před změřením (`M`) v operaci `TestBellState`:

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

Přidali jsme další operaci `SetQubitState` inicializující první qubit, abychom se ujistili, že je vždy v počátečním stavu `Zero`.

Stejně tak musíme resetovat druhý qubit, než ho na konci uvolníme.

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

Úplná rutina teď vypadá takto:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
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
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

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
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

Nová návratová hodnota (`agree`) počítá případy, kdy se měření prvního qubitu shodovalo s měřením druhého qubitu.

Spuštění kódu, který získáme:

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

Jak jsme uvedli v přehledu, statistika prvního qubitu se nezměnila (stále šance 50:50, že získáme 0 nebo 1), ale teď když změříme stav druhého qubitu, bude __vždy__ stejný, jako změřený stav toho prvního, protože jsou provázané!

## <a name="next-steps"></a>Další kroky

V kurzu [Grover Search](xref:microsoft.quantum.quickstarts.search) se dozvíte, jak sestavovat a spouštět hledání Grover, jeden z nejoblíbenějších výpočetních algoritmů a nabízí dobrý příklad Q# programu, který se dá použít k řešení reálných problémů s výpočetním využitím.  

[Začínáme s vývojovou sadou pro](xref:microsoft.quantum.welcome) všechna ta: doporučuje více způsobů, jak se naučit Q# a naprogramovat práci.
