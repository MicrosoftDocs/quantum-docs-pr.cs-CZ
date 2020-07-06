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
# <a name="develop-with-q-and-python"></a><span data-ttu-id="b84f4-102">Vývoj s využitím Q# a Pythonu</span><span class="sxs-lookup"><span data-stu-id="b84f4-102">Develop with Q# and Python</span></span>

<span data-ttu-id="b84f4-103">Nainstalujte sadu QDK pro vývoj hostitelských programů v Pythonu, volajících operace v Q#.</span><span class="sxs-lookup"><span data-stu-id="b84f4-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="b84f4-104">Instalace balíčku Pythonu `qsharp`</span><span class="sxs-lookup"><span data-stu-id="b84f4-104">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="b84f4-105">Instalace pomocí prostředí conda (doporučeno)</span><span class="sxs-lookup"><span data-stu-id="b84f4-105">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="b84f4-106">Nainstalujte aplikaci [Miniconda](https://docs.conda.io/en/latest/miniconda.html) nebo [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="b84f4-106">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span>

1. <span data-ttu-id="b84f4-107">Otevřete příkazový řádek aplikace Anaconda.</span><span class="sxs-lookup"><span data-stu-id="b84f4-107">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="b84f4-108">Případně pokud dáváte přednost použití PowerShellu nebo pwsh: otevřete prostředí, spusťte příkaz `conda init powershell` a pak prostředí zavřete a znovu otevřete.</span><span class="sxs-lookup"><span data-stu-id="b84f4-108">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="b84f4-109">Vytvořte a aktivujte nové prostředí conda s názvem `qsharp-env` s požadovanými balíčky (včetně Jupyter Notebook a IQ#) spuštěním následujících příkazů:</span><span class="sxs-lookup"><span data-stu-id="b84f4-109">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="b84f4-110">Spusťte příkaz `python -c "import qsharp"` ze stejného terminálu, abyste ověřili instalaci a naplnili místní mezipaměť balíčků všemi požadovanými součástmi QDK.</span><span class="sxs-lookup"><span data-stu-id="b84f4-110">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="b84f4-111">Instalace pomocí rozhraní .NET CLI a pip (rozšířené)</span><span class="sxs-lookup"><span data-stu-id="b84f4-111">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="b84f4-112">Požadavky:</span><span class="sxs-lookup"><span data-stu-id="b84f4-112">Prerequisites:</span></span>

    - <span data-ttu-id="b84f4-113">[Python](https://www.python.org/downloads/) 3.6 nebo novější</span><span class="sxs-lookup"><span data-stu-id="b84f4-113">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="b84f4-114">Správce balíčků Pythonu [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="b84f4-114">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="b84f4-115">Sada .NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="b84f4-115">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="b84f4-116">Nainstalujte `qsharp` – balíček Pythonu, který umožňuje spolupráci mezi Q# a Pythonem.</span><span class="sxs-lookup"><span data-stu-id="b84f4-116">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="b84f4-117">Nainstalujte IQ# – jádro primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a spouštění operací v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="b84f4-117">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="b84f4-118">Pokud se během kroku `dotnet iqsharp install` zobrazí chyba, otevřete nové okno terminálu a zkuste to znovu.</span><span class="sxs-lookup"><span data-stu-id="b84f4-118">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="b84f4-119">Pokud to pořád nefunguje, zkuste najít nainstalovaný nástroj `dotnet-iqsharp` (ve Windows `dotnet-iqsharp.exe`) a spusťte:</span><span class="sxs-lookup"><span data-stu-id="b84f4-119">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="b84f4-120">kde `/path/to/dotnet-iqsharp` nahraďte absolutní cestou k nástroji `dotnet-iqsharp` v systému souborů.</span><span class="sxs-lookup"><span data-stu-id="b84f4-120">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="b84f4-121">Obvykle bude ve složce `.dotnet/tools` ve vašem uživatelském profilu.</span><span class="sxs-lookup"><span data-stu-id="b84f4-121">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="b84f4-122">A to je vše!</span><span class="sxs-lookup"><span data-stu-id="b84f4-122">That's it!</span></span> <span data-ttu-id="b84f4-123">Nyní máte balíček Pythonu `qsharp` i jádro IQ# pro Jupyter, které poskytuje základní funkce pro kompilaci a provádění operací Q# z Pythonu a umožňuje používat poznámkové bloky Jupyter s kódem Q#.</span><span class="sxs-lookup"><span data-stu-id="b84f4-123">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provides the core functionality for compiling and executing Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="b84f4-124">Volba prostředí IDE</span><span class="sxs-lookup"><span data-stu-id="b84f4-124">Choose your IDE</span></span>

<span data-ttu-id="b84f4-125">I když Q# s Pythonem můžete použít v jakémkoli integrovaném vývojovém prostředí, důrazně doporučujeme pro vaše aplikace Q# + Python používat rozhraní IDE Visual Studio Code (VS Code).</span><span class="sxs-lookup"><span data-stu-id="b84f4-125">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="b84f4-126">Pomocí rozšíření QDK Visual Studio Code získáte přístup k rozsáhlejším funkcím, jako jsou například upozornění, zvýrazňování syntaxe, šablony projektů a další.</span><span class="sxs-lookup"><span data-stu-id="b84f4-126">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="b84f4-127">Pokud chcete použít VS Code:</span><span class="sxs-lookup"><span data-stu-id="b84f4-127">If you would like to use VS Code:</span></span>

- <span data-ttu-id="b84f4-128">Nainstalujte [VS Code](https://code.visualstudio.com/download) (Windows, Linux a Mac).</span><span class="sxs-lookup"><span data-stu-id="b84f4-128">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="b84f4-129">Nainstalujte [rozšíření QDK pro VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="b84f4-129">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="b84f4-130">Pokud chcete použít jiný editor, výše uvedené pokyny se nastavily.</span><span class="sxs-lookup"><span data-stu-id="b84f4-130">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-q-program"></a><span data-ttu-id="b84f4-131">Vytvoření prvního programu v jazyce Q#</span><span class="sxs-lookup"><span data-stu-id="b84f4-131">Write your first Q# program</span></span>

<span data-ttu-id="b84f4-132">Teď jste připravení ověřit instalaci balíčku Pythonu `qsharp` napsáním a spuštěním jednoduchého programu v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="b84f4-132">Now you are ready to verify your `qsharp` Python package installation by writing and executing a simple Q# program.</span></span>

1. <span data-ttu-id="b84f4-133">Vytvořte minimální operaci v jazyce Q# tím, že vytvoříte soubor s názvem `Operation.qs` a do něj přidáte následující kód:</span><span class="sxs-lookup"><span data-stu-id="b84f4-133">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="b84f4-134">Ve stejné složce, kde je soubor `Operation.qs`, vytvořte program v Pythonu s názvem `host.py` pro simulování operace v jazyce Q# `SampleQuantumRandomNumberGenerator()`:</span><span class="sxs-lookup"><span data-stu-id="b84f4-134">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    SampleQuantumRandomNumberGenerator.simulate()
    ```

1. <span data-ttu-id="b84f4-135">Z prostředí, které jste vytvořili během instalace (tj. prostředí conda nebo Python, kde jste nainstalovali `qsharp`), spusťte program:</span><span class="sxs-lookup"><span data-stu-id="b84f4-135">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="b84f4-136">Měl by se zobrazit výsledek vyvolané operace.</span><span class="sxs-lookup"><span data-stu-id="b84f4-136">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="b84f4-137">V tomto případě, kdy vaše operace generuje náhodný výsledek, se na obrazovce zobrazí buď `Zero`, nebo `One`.</span><span class="sxs-lookup"><span data-stu-id="b84f4-137">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="b84f4-138">Pokud program spouštíte opakovaně, měli by se oba výsledky zobrazovat přibližně stejně často.</span><span class="sxs-lookup"><span data-stu-id="b84f4-138">If you execute the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> * <span data-ttu-id="b84f4-139">Kód Pythonu je běžný program v Pythonu.</span><span class="sxs-lookup"><span data-stu-id="b84f4-139">The Python code is just a normal Python program.</span></span> <span data-ttu-id="b84f4-140">K psaní programu Pythonu a volání operací Q# můžete použít libovolné prostředí Pythonu, včetně poznámkových bloků Jupyter založených na Pythonu.</span><span class="sxs-lookup"><span data-stu-id="b84f4-140">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="b84f4-141">Program v Pythonu může importovat operace Q# z libovolného souboru .qs umístěného ve stejné složce jako samotný kód Pythonu.</span><span class="sxs-lookup"><span data-stu-id="b84f4-141">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b84f4-142">Další kroky</span><span class="sxs-lookup"><span data-stu-id="b84f4-142">Next steps</span></span>

<span data-ttu-id="b84f4-143">Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete podle tohoto kurzu napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="b84f4-143">Now that you have installed the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
