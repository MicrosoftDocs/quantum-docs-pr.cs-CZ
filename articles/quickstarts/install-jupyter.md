---
title: Vývoj v Q# a Jupyter Notebooks
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274053"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Vývoj v Q# a Jupyter Notebooks

Nainstalujte QDK pro vývoj operací Q# v Jupyter Notebooks.

Jupyter Notebooks umožňuje místní spouštění kódu přímo z poznámkového bloku a jeho doplnění o instrukce, poznámky a další obsah. Toto prostředí je ideální pro psaní kódu Q# s vloženými vysvětleními nebo pro interaktivní kurzy kvantových výpočtů. Podívejte se, co všechno k vytváření vlastních poznámkových bloků v Q# potřebujete.

IQ# (anglicky se vyslovuje i-q-sharp) je rozšíření sady .NET Core SDK primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a simulaci operací v jazyce Q#.

> [!NOTE]
> * V poznámkových blocích Jupyter s Q# můžete spouštět pouze kód Q# a operace nelze volat z externích hostitelských programů (např. souborů Python nebo C#). Toto prostředí není vhodné, pokud je vaším cílem kombinování externího klasického hostitelského programu s programem kvantovým.

1. Požadavky

    - [Python](https://www.python.org/downloads/) 3.6 nebo novější
    - [Poznámkový blok Jupyter](https://jupyter.readthedocs.io/en/latest/install.html)
    - [Sada .NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Nainstalujte balíček `iqsharp`.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Pokud se během kroku `dotnet iqsharp install` zobrazí chyba, otevřete nové okno terminálu a zkuste to znovu.
    > Pokud to pořád nefunguje, zkuste najít nainstalovaný nástroj `dotnet-iqsharp` (ve Windows `dotnet-iqsharp.exe`) a spusťte:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > kde `/path/to/dotnet-iqsharp` nahraďte absolutní cestou k nástroji `dotnet-iqsharp` v systému souborů.
    > Obvykle bude ve složce `.dotnet/tools` ve vašem uživatelském profilu.

1. Ověřte instalaci vytvořením aplikace `Hello World`.

    - Spusťte následující příkaz, kterým se spustí server poznámkového bloku:

        ```
        jupyter notebook
        ```

    - Jupyter Notebook otevřete tak, že zkopírujete a vložíte do prohlížeče adresu URL poskytnutou příkazovým řádkem.

    - Vytvořte poznámkový blok Jupyter s použitím jádra Q# a do první buňky poznámkového bloku přidejte následující kód:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Spusťte tuto buňku poznámkového bloku:

        ![Buňka poznámkového bloku Jupyter s kódem Q#](~/media/install-guide-jupyter.png)

        Ve výstupu buňky by se měl zobrazit text `SayHello`. Při spouštění v poznámkových blocích Jupyter se kód Q# kompiluje a výstupem poznámkového bloku jsou názvy nalezených operací.


    - V nové buňce spusťte právě vytvořenou operaci (v simulátoru) pomocí příkazu `%simulate`:

        ![Buňka poznámkového bloku Jupyter s magic příkazem %simulate](~/media/install-guide-jupyter-simulate.png)

        Na obrazovce by se měla zobrazit zpráva spolu s výsledkem vyvolané operace (v tomto případě uvidíme prázdný tuplet `()`, protože naše operace jednoduše vrací typ `Unit`).

## <a name="next-steps"></a>Další kroky

Teď, když jste nainstalovali QDK pro Q# v Jupyter Notebooks, můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng) v jazyce Q# tak, že kód Q# budete psát přímo v prostředí Jupyter Notebook.

Další příklady použití jazyka Q# v prostředí Jupyter Notebooks najdete v těchto tématech:
- [Úvod do Q# a Jupyter Notebooks](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). V tomto článku najdete poznámkový blok Jupyter s kódem Q#, který ukazuje, jak jazyk Q# v tomto prostředí používat.
- [Quantum Katas](xref:microsoft.quantum.overview.katas), open source sbírka kurzů s vlastním tempem a sady programovacích cvičení ve formě poznámkových bloků Jupyter s kódem Q#. [Poznámkové bloky kurzů Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) jsou dobrým výchozím bodem. Quantum Katas se zaměřují současně na výuku základních prvků kvantových výpočtů i na programování v jazyce Q#. Skvělým způsobem předvádějí, jaký typ obsahu můžete pomocí poznámkových bloků Jupyter s kódem Q# vytvářet.
