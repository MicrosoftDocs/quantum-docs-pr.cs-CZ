---
title: Spuštění vyhledávacího algoritmu Grover v Q# sadě – pro vývojová prostředí
description: Sestavte Q# projekt, který ukazuje algoritmus Grover, jeden z kanonických algoritmů pro stav.
author: cgranade
ms.author: chgranad
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
no-loc:
- Q#
- $$v
ms.openlocfilehash: 86c6a651a117b788eb4c8fdd805ead7ab8f54dd7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834801"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a>Kurz: Implementace Groverova vyhledávacího algoritmu v jazyku Q\#

V tomto kurzu se dozvíte, jak zkompilovat a spustit Groverův vyhledávácí algoritmus, který zrychluje hledání v nestrukturovaných datech.  Grover je jedním z nejoblíbenějších výpočetních hodnot pro procesory a tato poměrně malá Q# implementace poskytuje představu o některých výhodách programování řešení s velkým množstvím programovacích procesorů, které jsou náročné Q# na výpočetní jazyk.  Na konci průvodce se zobrazí výstup simulace, který ukazuje úspěšné vyhledání konkrétního řetězce v seznamu neuspořádaných položek za zlomek času, než by trvalo prohledání celého seznamu v klasickém počítači.

Groverův algoritmus hledá konkrétní položky v seznamu nestrukturovaných dat. Může například odpovědět na otázku: Je tato karta vytažená z balíčku karet srdcové eso? Popisek konkrétní položky se nazývá _označený vstup_.

S použitím Groverova vyhledávacího algoritmu je zaručeno, že kvantový počítač toto hledání spustí v méně krocích, než je počet položek seznamu, ve kterém hledáte – něco, co žádný klasický algoritmus nedokáže. Zvýšení rychlosti je v případě balíčku karet zanedbatelné; u seznamů obsahujících milióny nebo miliardy položek je však značné.

Groverův vyhledávací algoritmus je možné sestavit s pouhými několika řádky kódu.

## <a name="prerequisites"></a>Požadavky

- Sada Microsoft [Quantum Development Kit][install].

## <a name="what-does-grovers-search-algorithm-do"></a>Co Groverův vyhledávací algoritmus dělá?

Groverův algoritmus se ptá, jestli je určitá položka v seznamu tou, kterou hledáme. Dosáhne toho sestrojením kvantové superpozice indexů seznamu s každým koeficientem (amplitudou pravděpodobnosti), který představuje pravděpodobnost toho, že daný index je hledaným indexem.

Jádrem algoritmu jsou dva kroky, které postupně zvyšují koeficient indexu, který hledáme, dokud se amplituda pravděpodobnosti tohoto koeficientu nepřiblíží k hodnotě 1.

Počet postupných zvýšení je menší než počet položek v seznamu. Proto Groverův algoritmus provádí hledání v méně krocích než jakýkoli klasický algoritmus.

![Funkční schéma Groverova vyhledávacího algoritmu](~/media/grover.png)

## <a name="write-the-code"></a>Psaní kódu

1. Pomocí vývojářské sady pro práci s více podsystému [vytvořte nový Q# projekt pro aplikaci](xref:microsoft.quantum.install.standalone). Nazvěte projekt `Grover`.

1. Do souboru `Program.qs` v projektu přidejte tento kód:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. Definujte seznam, ve kterém hledáme, tak, že vytvoříte nový soubor `Reflections.qs` a vložíte do něj tento kód:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    Operace `ReflectAboutMarked` definuje označený vstup, který hledáte: řetězec střídajících se nul a jedniček. V tomto příkladu je zadán pevný označený vstup. Je možné rozšířit ho a hledat jiné vstupy nebo obecně jakýkoli vstup.

1. V dalším kroku spusťte nový Q# program, abyste našli položku označenou `ReflectAboutMarked` .

### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a>Q# aplikace se sadou Visual Studio nebo Visual Studio Code

Program spustí operaci nebo funkci označenou `@EntryPoint()` atributem simulátoru nebo Estimator prostředku v závislosti na konfiguraci projektu a možnostech příkazového řádku.

V aplikaci Visual Studio stačí stisknout kombinaci kláves CTRL + F5 ke spuštění skriptu.

V editoru VS Code při prvním použití sestavte `Program.qs` zadáním následujícího příkazu na terminálu:

```Command line
dotnet build
```

Pro následná spuštění není potřeba ho sestavovat znovu. Pokud ho chcete spustit, zadejte následující příkaz a stiskněte Enter:

```Command line
dotnet run --no-build
```

Na terminálu by se měla zobrazit následující zpráva:

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

Důvodem je to, že jste nezadali počet qubits, které jste chtěli použít, takže terminál zobrazí příkazy, které jsou k dispozici pro spustitelný program. Pokud chceme použít 5 qubits, měli byste zadat:

```Command line
dotnet run --n-qubits 5
```

Po stisknutí klávesy Enter by se měl zobrazit následující výstup:

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a>Další kroky

Pokud jste se seznámili s tímto kurzem, podívejte se na některé z níže uvedených prostředků, kde se dozvíte víc o tom, jak můžete použít Q# k psaní vlastních aplikací s využitím.

- [Zpět na Začínáme pomocí průvodce sady QDK](xref:microsoft.quantum.welcome)
- Vyzkoušejte [ukázku](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/database-search) obecnějšího Groverova vyhledávacího algoritmu
- [Další informace o Groverově vyhledávání v kvantových katách](xref:microsoft.quantum.overview.katas)
- Další informace o [zvětšování amplitudy][amplitude-amplification], technice kvantových výpočtů, která stojí za Groverovým vyhledávacím algoritmem
- [Koncepce kvantových výpočtů](xref:microsoft.quantum.concepts.intro)
- [Ukázky sady Quantum Development Kit](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
