---
title: Vývoj s využitím aplikací Jupyter Notebook s podporou Q#
description: Naučte se vytvářet aplikace v Q# pomocí poznámkových bloků Jupyter.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 51de510907ea087d1f23d3ff65d268d6d455a493
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834308"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a>Vývoj s využitím aplikací Jupyter Notebook s podporou Q#

Nainstalujte QDK pro vývoj operací Q# v aplikacích Jupyter Notebook s podporou Q#.

Jupyter Notebook umožňuje místní spouštění kódu přímo z poznámkového bloku a jeho doplnění o instrukce, poznámky a další obsah. Toto prostředí je ideální pro psaní kódu Q# s vloženými vysvětleními nebo pro interaktivní kurzy kvantových výpočtů. Podívejte se, co všechno k vytváření vlastních poznámkových bloků v Q# potřebujete.

## <a name="install-the-ino-locq-jupyter-kernel"></a>Instalace jádra IQ# Jupyter

IQ# (anglicky se vyslovuje i-q-sharp) je rozšíření sady .NET Core SDK primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a simulaci operací v jazyce Q#.

### <a name="install-using-conda-recommended"></a>[Instalace pomocí prostředí conda (doporučeno)](#tab/tabid-conda)

1. Nainstalujte aplikaci [Miniconda](https://docs.conda.io/en/latest/miniconda.html) nebo [Anaconda](https://www.anaconda.com/products/individual#Downloads). **Poznámka:** Vyžaduje se 64 bitová instalace.

1. Otevřete příkazový řádek aplikace Anaconda.

   - Případně pokud dáváte přednost použití PowerShellu nebo pwsh: otevřete prostředí, spusťte příkaz `conda init powershell` a pak prostředí zavřete a znovu otevřete.

1. Spuštěním následujících příkazů vytvořte a aktivujte nové prostředí conda s názvem `qsharp-env` s požadovanými balíčky (včetně Jupyter Notebook a IQ#):

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

A to je vše! Nyní máte jádro IQ# pro Jupyter, které poskytuje základní funkce pro kompilaci a spouštění operací Q# z aplikací Jupyter Notebook s podporou Q#.

## <a name="create-your-first-no-locq-notebook"></a>Vytvoření prvního poznámkového bloku v Q#

Teď jste připravení ověřit instalaci aplikace Jupyter Notebook s podporou Q# napsáním a spuštěním jednoduché operace v jazyce Q#.

1. Z prostředí, které jste vytvořili během instalace (tj. buď z prostředí conda, které jste vytvořili, nebo prostředí Pythonu, do kterého jste nainstalovali Jupyter), spusťte následující příkaz, který spustí server Jupyter Notebook:

    ```
    jupyter notebook
    ```

    - Pokud se Jupyter Notebook neotevřete automaticky, zkopírujte a vložte do prohlížeče adresu URL poskytnutou příkazovým řádkem.

1. Zvolte **New (Nový) → Q#** a vytvořte Jupyter Notebook s použitím jádra Q#. Do první buňky poznámkového bloku přidejte následující kód:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. Spusťte tuto buňku poznámkového bloku:

    ![Buňka aplikace Jupyter Notebook s kódem Q#](~/media/install-guide-jupyter.png)

    Ve výstupu buňky by se měl zobrazit text `SampleQuantumRandomNumberGenerator`. Při spouštění v aplikacích Jupyter Notebook se kód Q# kompiluje a výstupem buňky jsou názvy všech nalezených operací.

1. V nové buňce spusťte právě vytvořenou operaci (v simulátoru) pomocí příkazu `%simulate`:

    ![Buňka poznámkového bloku Jupyter s magic příkazem %simulate](~/media/install-guide-jupyter-simulate.png)

    Měl by se zobrazit výsledek vyvolané operace. V tomto případě, kdy vaše operace generuje náhodný výsledek, se na obrazovce zobrazí buď `Zero`, nebo `One`. Pokud buňku spouštíte opakovaně, měli by se oba výsledky zobrazovat přibližně stejně často.

## <a name="next-steps"></a>Další kroky

Teď, když jste nainstalovali QDK pro aplikace Jupyter Notebook s podporou Q#, můžete napsat a spustit svůj [první kvantový program](xref:microsoft.quantum.quickstarts.qrng) tak, že kód Q# budete psát přímo v prostředí Jupyter Notebook.

Další příklady použití aplikací Jupyter Notebook s podporou Q# najdete v těchto tématech:

- [Úvod k Q# a aplikacím Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). V tomto článku najdete Jupyter Notebook s podporou Q#, který ukazuje další podrobnosti, jak používat jazyk Q# v prostředí Jupyter.
- [Quantum Katas](xref:microsoft.quantum.overview.katas), opensourcová kolekce kurzů umožňujících postupovat vlastním tempem a sady programovacích cvičení ve formě aplikací Jupyter Notebook s podporou Q#. [Poznámkové bloky kurzů Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) jsou dobrým výchozím bodem. Quantum Katas se zaměřují současně na výuku základních prvků kvantových výpočtů i na programování v jazyce Q#. Skvělým způsobem předvádějí, jaký typ obsahu můžete pomocí aplikací Jupyter Notebook s podporou Q# vytvářet.
