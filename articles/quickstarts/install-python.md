---
title: Vývoj s využitím Q# a Pythonu
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 7fbbb81b1ee51bff74b287745bf4447004a0254c
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885537"
---
# <a name="develop-with-q-and-python"></a>Vývoj s využitím Q# a Pythonu

Nainstalujte sadu QDK pro vývoj hostitelských programů v Pythonu, volajících operace v Q#.

## <a name="install-the-qsharp-python-package"></a>Instalace balíčku Pythonu `qsharp`

### <a name="install-using-conda-recommended"></a>[Instalace pomocí prostředí conda (doporučeno)](#tab/tabid-conda)

1. Nainstalujte aplikaci [Miniconda](https://docs.conda.io/en/latest/miniconda.html) nebo [Anaconda](https://www.anaconda.com/products/individual#Downloads).

1. Otevřete příkazový řádek aplikace Anaconda.

   - Případně pokud dáváte přednost použití PowerShellu nebo pwsh: otevřete prostředí, spusťte příkaz `conda init powershell` a pak prostředí zavřete a znovu otevřete.

1. Vytvořte a aktivujte nové prostředí conda s názvem `qsharp-env` s požadovanými balíčky (včetně Jupyter Notebook a IQ#) spuštěním následujících příkazů:

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. Spusťte příkaz `python -c "import qsharp"` ze stejného terminálu, abyste ověřili instalaci a naplnili místní mezipaměť balíčků všemi požadovanými součástmi QDK.

### <a name="install-using-net-cli-and-pip-advanced"></a>[Instalace pomocí rozhraní .NET CLI a pip (rozšířené)](#tab/tabid-dotnetcli)

1. Požadavky:

    - [Python](https://www.python.org/downloads/) 3.6 nebo novější
    - Správce balíčků Pythonu [PIP](https://pip.pypa.io/en/stable/installing)
    - [Sada .NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Nainstalujte `qsharp` – balíček Pythonu, který umožňuje spolupráci mezi Q# a Pythonem.

    ```
    pip install qsharp
    ```

1. Nainstalujte IQ# – jádro primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a spouštění operací v jazyce Q#.

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

A to je vše! Nyní máte balíček Pythonu `qsharp` i jádro IQ# pro Jupyter, které poskytuje základní funkce pro kompilaci a provádění operací Q# z Pythonu a umožňuje používat poznámkové bloky Jupyter s kódem Q#.

## <a name="choose-your-ide"></a>Volba prostředí IDE

I když Q# s Pythonem můžete použít v jakémkoli integrovaném vývojovém prostředí, důrazně doporučujeme pro vaše aplikace Q# + Python používat rozhraní IDE Visual Studio Code (VS Code). Pomocí rozšíření QDK Visual Studio Code získáte přístup k rozsáhlejším funkcím, jako jsou například upozornění, zvýrazňování syntaxe, šablony projektů a další.

Pokud chcete použít VS Code:

- Nainstalujte [VS Code](https://code.visualstudio.com/download) (Windows, Linux a Mac).
- Nainstalujte [rozšíření QDK pro VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Pokud chcete použít jiný editor, výše uvedené pokyny se nastavily.

## <a name="write-your-first-q-program"></a>Vytvoření prvního programu v jazyce Q#

Teď jste připravení ověřit instalaci balíčku Pythonu `qsharp` napsáním a spuštěním jednoduchého programu v jazyce Q#.

1. Vytvořte minimální operaci v jazyce Q# tím, že vytvoříte soubor s názvem `Operation.qs` a do něj přidáte následující kód:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. Ve stejné složce, kde je soubor `Operation.qs`, vytvořte program v Pythonu s názvem `host.py` pro simulování operace v jazyce Q# `SampleQuantumRandomNumberGenerator()`:

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    SampleQuantumRandomNumberGenerator.simulate()
    ```

1. Z prostředí, které jste vytvořili během instalace (tj. prostředí conda nebo Python, kde jste nainstalovali `qsharp`), spusťte program:

    ```
    python host.py
    ```

1. Měl by se zobrazit výsledek vyvolané operace. V tomto případě, kdy vaše operace generuje náhodný výsledek, se na obrazovce zobrazí buď `Zero`, nebo `One`. Pokud program spouštíte opakovaně, měli by se oba výsledky zobrazovat přibližně stejně často.

> [!NOTE]
> * Kód Pythonu je běžný program v Pythonu. K psaní programu Pythonu a volání operací Q# můžete použít libovolné prostředí Pythonu, včetně poznámkových bloků Jupyter založených na Pythonu. Program v Pythonu může importovat operace Q# z libovolného souboru .qs umístěného ve stejné složce jako samotný kód Pythonu.

## <a name="next-steps"></a>Další kroky

Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete podle tohoto kurzu napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).
