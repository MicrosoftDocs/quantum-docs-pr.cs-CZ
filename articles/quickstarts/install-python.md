---
title: Vývoj s využitím Q# a Pythonu
description: Naučte se vytvářet aplikace v Q# pomocí Pythonu.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.python
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1ec40b6f1b7a8d9144860e3b8cfd554eb51bae81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844271"
---
# <a name="develop-with-no-locq-and-python"></a><span data-ttu-id="7a2ac-103">Vývoj s využitím Q# a Pythonu</span><span class="sxs-lookup"><span data-stu-id="7a2ac-103">Develop with Q# and Python</span></span>

<span data-ttu-id="7a2ac-104">Nainstalujte sadu QDK pro vývoj hostitelských programů v Pythonu pro volání operací v Q#.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-104">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="7a2ac-105">Instalace balíčku Pythonu `qsharp`</span><span class="sxs-lookup"><span data-stu-id="7a2ac-105">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="7a2ac-106">Instalace pomocí prostředí conda (doporučeno)</span><span class="sxs-lookup"><span data-stu-id="7a2ac-106">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="7a2ac-107">Nainstalujte aplikaci [Miniconda](https://docs.conda.io/en/latest/miniconda.html) nebo [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="7a2ac-107">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="7a2ac-108">**Poznámka:** Vyžaduje se 64 bitová instalace.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-108">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="7a2ac-109">Otevřete příkazový řádek aplikace Anaconda.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-109">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="7a2ac-110">Případně pokud dáváte přednost použití PowerShellu nebo pwsh: otevřete prostředí, spusťte příkaz `conda init powershell` a pak prostředí zavřete a znovu otevřete.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-110">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="7a2ac-111">Spuštěním následujících příkazů vytvořte a aktivujte nové prostředí conda s názvem `qsharp-env` s požadovanými balíčky (včetně Jupyter Notebook a IQ#):</span><span class="sxs-lookup"><span data-stu-id="7a2ac-111">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="7a2ac-112">Spusťte příkaz `python -c "import qsharp"` ze stejného terminálu, abyste ověřili instalaci a naplnili místní mezipaměť balíčků všemi požadovanými součástmi QDK.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-112">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="7a2ac-113">Instalace pomocí rozhraní .NET CLI a pip (rozšířené)</span><span class="sxs-lookup"><span data-stu-id="7a2ac-113">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="7a2ac-114">Požadavky:</span><span class="sxs-lookup"><span data-stu-id="7a2ac-114">Prerequisites:</span></span>

    - <span data-ttu-id="7a2ac-115">[Python](https://www.python.org/downloads/) 3.6 nebo novější</span><span class="sxs-lookup"><span data-stu-id="7a2ac-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="7a2ac-116">Správce balíčků Pythonu [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="7a2ac-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="7a2ac-117">Sada .NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="7a2ac-117">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="7a2ac-118">Nainstalujte `qsharp` – balíček Pythonu, který umožňuje spolupráci mezi Q# a Pythonem.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-118">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="7a2ac-119">Nainstalujte IQ# – jádro primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a spouštění operací v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-119">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and running Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="7a2ac-120">Pokud se během kroku `dotnet iqsharp install` zobrazí chyba, otevřete nové okno terminálu a zkuste to znovu.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-120">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="7a2ac-121">Pokud to pořád nefunguje, zkuste najít nainstalovaný nástroj `dotnet-iqsharp` (ve Windows `dotnet-iqsharp.exe`) a spusťte:</span><span class="sxs-lookup"><span data-stu-id="7a2ac-121">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="7a2ac-122">kde `/path/to/dotnet-iqsharp` nahraďte absolutní cestou k nástroji `dotnet-iqsharp` v systému souborů.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-122">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="7a2ac-123">Obvykle bude ve složce `.dotnet/tools` ve vašem uživatelském profilu.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-123">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
<span data-ttu-id="7a2ac-124">\*\*_</span><span class="sxs-lookup"><span data-stu-id="7a2ac-124">\*\*_</span></span>

<span data-ttu-id="7a2ac-125">A to je vše!</span><span class="sxs-lookup"><span data-stu-id="7a2ac-125">That's it!</span></span> <span data-ttu-id="7a2ac-126">Nyní máte k dispozici balíček Pythonu `qsharp` i jádro IQ# pro Jupyter, které poskytuje základní funkce pro kompilaci a spouštění operací Q# z Pythonu a umožňuje používat aplikace Jupyter Notebook s podporou Q#.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-126">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provide the core functionality for compiling and running Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="7a2ac-127">Volba prostředí IDE</span><span class="sxs-lookup"><span data-stu-id="7a2ac-127">Choose your IDE</span></span>

<span data-ttu-id="7a2ac-128">I když Q# s Pythonem můžete použít v jakémkoli integrovaném vývojovém prostředí, důrazně doporučujeme pro vaše aplikace v Q# a Pythonu používat rozhraní IDE Visual Studio Code (VS Code).</span><span class="sxs-lookup"><span data-stu-id="7a2ac-128">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="7a2ac-129">Pomocí rozšíření QDK Visual Studio Code získáte přístup k rozsáhlejším funkcím, jako jsou například upozornění, zvýrazňování syntaxe, šablony projektů a další.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-129">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="7a2ac-130">Pokud chcete použít VS Code:</span><span class="sxs-lookup"><span data-stu-id="7a2ac-130">If you would like to use VS Code:</span></span>

- <span data-ttu-id="7a2ac-131">Nainstalujte [VS Code](https://code.visualstudio.com/download) (Windows, Linux a Mac).</span><span class="sxs-lookup"><span data-stu-id="7a2ac-131">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="7a2ac-132">Nainstalujte [rozšíření QDK pro VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="7a2ac-132">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="7a2ac-133">Pokud chcete použít jiný editor, výše uvedené pokyny se nastavily.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-133">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-no-locq-program"></a><span data-ttu-id="7a2ac-134">Vytvoření prvního programu v jazyce Q#</span><span class="sxs-lookup"><span data-stu-id="7a2ac-134">Write your first Q# program</span></span>

<span data-ttu-id="7a2ac-135">Teď jste připravení ověřit instalaci balíčku Pythonu `qsharp` napsáním a spuštěním jednoduchého programu v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-135">Now you are ready to verify your `qsharp` Python package installation by writing and running a simple Q# program.</span></span>

1. <span data-ttu-id="7a2ac-136">Vytvořte minimální operaci v jazyce Q# tím, že vytvoříte soubor s názvem `Operation.qs` a do něj přidáte následující kód:</span><span class="sxs-lookup"><span data-stu-id="7a2ac-136">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="7a2ac-137">Ve stejné složce, kde je soubor `Operation.qs`, vytvořte program v Pythonu s názvem `host.py` pro simulování operace Q# v `SampleQuantumRandomNumberGenerator()`:</span><span class="sxs-lookup"><span data-stu-id="7a2ac-137">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. <span data-ttu-id="7a2ac-138">Z prostředí, které jste vytvořili během instalace (tj. prostředí conda nebo Python, kde jste nainstalovali `qsharp`), spusťte program:</span><span class="sxs-lookup"><span data-stu-id="7a2ac-138">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="7a2ac-139">Měl by se zobrazit výsledek vyvolané operace.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-139">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="7a2ac-140">V tomto případě, kdy vaše operace generuje náhodný výsledek, se na obrazovce zobrazí buď `0`, nebo `1`.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-140">In this case, because your operation generates a random result, you will see either `0` or `1` printed on the screen.</span></span> <span data-ttu-id="7a2ac-141">Pokud program spouštíte opakovaně, měli by se oba výsledky zobrazovat přibližně stejně často.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-141">If you run the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> <span data-ttu-id="7a2ac-142">_ Kód Pythonu je pouze běžný program v Pythonu.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-142">_ The Python code is just a normal Python program.</span></span> <span data-ttu-id="7a2ac-143">K psaní programu Pythonu a volání operací Q# můžete použít libovolné prostředí Pythonu, včetně aplikací Jupyter Notebook založených na Pythonu.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-143">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="7a2ac-144">Program v Pythonu může importovat operace Q# z libovolného souboru .qs umístěného ve stejné složce jako samotný kód Pythonu.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-144">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7a2ac-145">Další kroky</span><span class="sxs-lookup"><span data-stu-id="7a2ac-145">Next steps</span></span>

<span data-ttu-id="7a2ac-146">Teď máte sadu Quantum Development Kit otestovanou v upřednostňovaném prostředí a můžete podle tohoto kurzu napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="7a2ac-146">Now that you have tested the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
