---
title: Vývoj v Q# a Jupyter Notebooks
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: bbd1f58ba7de205e452be7bac72b5fd78e7acd56
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871446"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Vývoj v Q# a Jupyter Notebooks

Nainstalujte QDK pro vývoj operací Q# v Jupyter Notebooks.

Jupyter Notebooks umožňuje místní spouštění kódu přímo z poznámkového bloku a jeho doplnění o instrukce, poznámky a další obsah. Toto prostředí je ideální pro psaní kódu Q# s vloženými vysvětleními nebo pro interaktivní kurzy kvantových výpočtů. Podívejte se, co všechno k vytváření vlastních poznámkových bloků v Q# potřebujete.

> [!NOTE]
> * V poznámkových blocích Jupyter s kódem Q# můžete spouštět pouze kód Q# a operace nelze volat z externích hostitelských programů (např. souborů Python nebo C#). Toto prostředí není vhodné, pokud je vaším cílem kombinování externího klasického hostitelského programu s programem kvantovým.

## <a name="install-the-iq-jupyter-kernel"></a>Instalace jádra IQ# Jupyter

IQ# (anglicky se vyslovuje i-q-sharp) je rozšíření sady .NET Core SDK primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a simulaci operací v jazyce Q#.

### <a name="install-using-conda-recommended"></a>[Instalace pomocí prostředí conda (doporučeno)](#tab/tabid-conda)

1. Nainstalujte aplikaci [Miniconda](https://docs.conda.io/en/latest/miniconda.html) nebo [Anaconda](https://www.anaconda.com/products/individual#Downloads). **Poznámka:** Vyžaduje se 64 bitová instalace.

1. Otevřete příkazový řádek aplikace Anaconda.

   - Případně pokud dáváte přednost použití PowerShellu nebo pwsh: otevřete prostředí, spusťte příkaz `conda init powershell` a pak prostředí zavřete a znovu otevřete.

1. Vytvořte a aktivujte nové prostředí conda s názvem `qsharp-env` s požadovanými balíčky (včetně Jupyter Notebook a IQ#) spuštěním následujících příkazů:

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. Spusťte příkaz `python -c "import qsharp"` ze stejného terminálu, abyste ověřili instalaci a naplnili místní mezipaměť balíčků všemi požadovanými součástmi QDK.

### <a name="install-using-net-cli-advanced"></a>[Instalace pomocí rozhraní .NET CLI (rozšířené)](#tab/tabid-dotnetcli)

1. Požadavky:

    - [Python](https://www.python.org/downloads/) 3.6 nebo novější
    - [Poznámkový blok Jupyter](https://jupyter.readthedocs.io/en/latest/install.html)
    - [Sada .NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Nainstalujte balíček `Microsoft.Quantum.IQSharp`.

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
    
***

A to je vše! Nyní máte jádro IQ# pro Jupyter, které poskytuje základní funkce pro kompilaci a provádění operací Q# z poznámkových bloků Jupyter s kódem Q#.

## <a name="create-your-first-q-notebook"></a>Vytvoření prvního poznámkového bloku Q#

Teď jste připravení ověřit instalaci Q# Jupyter Notebook napsáním a spuštěním jednoduché operace v jazyce Q#.

1. Z prostředí, které jste vytvořili během instalace (tj. buď z prostředí conda, které jste vytvořili, nebo prostředí Pythonu, do kterého jste nainstalovali Jupyter), spusťte následující příkaz, který spustí server Jupyter Notebook:

    ```
    jupyter notebook
    ```

    - Pokud se Jupyter Notebook neotevřete automaticky, zkopírujte a vložte do prohlížeče adresu URL poskytnutou příkazovým řádkem.

1. Zvolte New (Nový) → Q# a vytvořte poznámkový blok Jupyter s použitím jádra Q#. Do první buňky poznámkového bloku přidejte následující kód:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. Spusťte tuto buňku poznámkového bloku:

    ![Buňka poznámkového bloku Jupyter s kódem Q#](~/media/install-guide-jupyter.png)

    Ve výstupu buňky by se měl zobrazit text `SampleQuantumRandomNumberGenerator`. Při spouštění v poznámkových blocích Jupyter se kód Q# kompiluje a výstupem buňky jsou názvy všech nalezených operací.

1. V nové buňce spusťte právě vytvořenou operaci (v simulátoru) pomocí příkazu `%simulate`:

    ![Buňka poznámkového bloku Jupyter s magic příkazem %simulate](~/media/install-guide-jupyter-simulate.png)

    Měl by se zobrazit výsledek vyvolané operace. V tomto případě, kdy vaše operace generuje náhodný výsledek, se na obrazovce zobrazí buď `Zero`, nebo `One`. Pokud buňku spouštíte opakovaně, měli by se oba výsledky zobrazovat přibližně stejně často.

## <a name="next-steps"></a>Další kroky

Teď, když jste nainstalovali QDK pro poznámkové bloky Jupyter s kódem Q#, můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng) v jazyce Q# tak, že kód Q# budete psát přímo v prostředí Jupyter Notebook.

Další příklady použití jazyka Q# v prostředí Jupyter Notebooks najdete v těchto tématech:

- [Úvod do Q# a Jupyter Notebooks](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). V tomto článku najdete poznámkový blok Jupyter s kódem Q#, který ukazuje další podrobnosti, jak používat jazyk Q# v prostředí Jupyter.
- [Quantum Katas](xref:microsoft.quantum.overview.katas), open source sbírka kurzů s vlastním tempem a sady programovacích cvičení ve formě poznámkových bloků Jupyter s kódem Q#. [Poznámkové bloky kurzů Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) jsou dobrým výchozím bodem. Quantum Katas se zaměřují současně na výuku základních prvků kvantových výpočtů i na programování v jazyce Q#. Skvělým způsobem předvádějí, jaký typ obsahu můžete pomocí poznámkových bloků Jupyter s kódem Q# vytvářet.
