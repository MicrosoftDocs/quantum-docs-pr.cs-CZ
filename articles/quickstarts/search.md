---
title: Spuštění Groverova vyhledávacího algoritmu v jazyku Q# – Quantum Development Kit
description: Sestavte projekt v jazyku Q#, který demonstruje Groverův algoritmus – jeden z kanonických kvantových algoritmů.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: c1fd578fdb3d56a7b48972e6ccc9b1605047fe36
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820347"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a>Rychlý start: Implementace Groverova vyhledávacího algoritmu v jazyku Q#

V tomto rychlém startu se dozvíte, jak zkompilovat a spustit Groverovo hledání a urychlit hledání nestrukturovaných dat.  Groverovo hledání je jedním z nejoblíbenějších kvantových výpočetních algoritmů a tato poměrně malá implementace v jazyce Q# poskytuje představu o některých výhodách programování kvantových řešení pomocí kvantového programovacího jazyka Q# vysoké úrovně při vyjádření kvantových algoritmů.  Na konci průvodce se zobrazí výstup simulace, který ukazuje úspěšné vyhledání konkrétního řetězce v seznamu neuspořádaných položek za zlomek času, než by trvalo prohledání celého seznamu v klasickém počítači.

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

1. S použitím sady Quantum Development Kit [vytvořte nový projekt v jazyku Q#](xref:microsoft.quantum.howto.createproject) s názvem `Grover` ve vývojovém prostředí podle vašeho výběru.

1. Do souboru `Operations.qs` v projektu přidejte tento kód:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-23" highlight="5,27":::

1. Definujte seznam, ve kterém hledáme, tak, že vytvoříte nový soubor `Reflections.qs` a vložíte do něj tento kód:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    Operace `ReflectAboutMarked` definuje označený vstup, který hledáte: řetězec střídajících se nul a jedniček. V tomto příkladu je zadán pevný označený vstup. Je možné rozšířit ho a hledat jiné vstupy nebo obecně jakýkoli vstup.

1. Dále spusťte nový program v jazyku Q# a vyhledejte položku označenou operací `ReflectAboutMarked`.

    ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[Python s Visual Studio Code nebo příkazovým řádkem](#tab/tabid-python)

    Pokud chcete nový program v jazyku Q# spustit z Pythonu, uložte jako soubor `host.py` tento kód:

    :::code language="python" source="~/quantum/samples/algorithms/simple-grover/host.py" range="9-14":::

    Pak můžete hostitelský program Pythonu spustit z příkazového řádku:

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[C# s Visual Studio Code nebo příkazovým řádkem](#tab/tabid-csharp)

    Pokud chcete nový program v jazyku Q# spustit z C#, upravte soubor `Driver.cs` tak, aby obsahoval tento kód C#:

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    Pak můžete hostitelský program C# spustit z příkazového řádku:

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[C# s Visual Studiem 2019](#tab/tabid-vs2019)

    Pokud chcete nový program v jazyku Q# spustit z C# v sadě Visual Studio, upravte soubor `Driver.cs` tak, aby obsahoval tento kód C#:

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    Pak stiskněte klávesu F5, program se spustí a automaticky se zobrazí nové okno s následujícími výsledky: 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    Operace `ReflectAboutMarked` se volá jen čtyřikrát, program v jazyku Q# však našel vstup „01010“ mezi $2^{5} = 32$ možnými vstupy!

## <a name="next-steps"></a>Další kroky

Pokud se vám tento rychlý start líbil, podívejte se na některé prostředky níže, ze kterých se dozvíte víc o tom, jak můžete v jazyku Q# psát vlastní kvantové aplikace:

- [Zpět na Začínáme pomocí průvodce sady QDK](xref:microsoft.quantum.welcome)
- Vyzkoušejte [ukázku](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) obecnějšího Groverova vyhledávacího algoritmu
- [Další informace o Groverově vyhledávání v kvantových katách](xref:microsoft.quantum.overview.katas)
- Další informace o [zvětšování amplitudy](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), technice kvantových výpočtů, která stojí za Groverovým vyhledávacím algoritmem
- [Koncepce kvantových výpočtů](xref:microsoft.quantum.concepts.intro)
- [Ukázky sady Quantum Development Kit](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
