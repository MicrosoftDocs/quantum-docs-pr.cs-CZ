---
title: Vývoj s využitím Q# a Pythonu
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
no-loc:
- Q#
- $$v
ms.openlocfilehash: 01a5c31a7a920a69f4f90701d370f3a772d2c4d2
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866736"
---
# <a name="develop-with-no-locq-and-python"></a><span data-ttu-id="3d9cc-102">Vývoj s využitím Q# a Pythonu</span><span class="sxs-lookup"><span data-stu-id="3d9cc-102">Develop with Q# and Python</span></span>

<span data-ttu-id="3d9cc-103">Nainstalujte sadu QDK pro vývoj hostitelských programů v Pythonu pro volání operací v Q#.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="3d9cc-104">Instalace balíčku Pythonu `qsharp`</span><span class="sxs-lookup"><span data-stu-id="3d9cc-104">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="3d9cc-105">Instalace pomocí prostředí conda (doporučeno)</span><span class="sxs-lookup"><span data-stu-id="3d9cc-105">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="3d9cc-106">Nainstalujte aplikaci [Miniconda](https://docs.conda.io/en/latest/miniconda.html) nebo [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="3d9cc-106">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="3d9cc-107">**Poznámka:** Vyžaduje se 64 bitová instalace.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-107">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="3d9cc-108">Otevřete příkazový řádek aplikace Anaconda.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-108">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="3d9cc-109">Případně pokud dáváte přednost použití PowerShellu nebo pwsh: otevřete prostředí, spusťte příkaz `conda init powershell` a pak prostředí zavřete a znovu otevřete.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-109">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="3d9cc-110">Spuštěním následujících příkazů vytvořte a aktivujte nové prostředí conda s názvem `qsharp-env` s požadovanými balíčky (včetně Jupyter Notebook a IQ#):</span><span class="sxs-lookup"><span data-stu-id="3d9cc-110">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="3d9cc-111">Spusťte příkaz `python -c "import qsharp"` ze stejného terminálu, abyste ověřili instalaci a naplnili místní mezipaměť balíčků všemi požadovanými součástmi QDK.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-111">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="3d9cc-112">Instalace pomocí rozhraní .NET CLI a pip (rozšířené)</span><span class="sxs-lookup"><span data-stu-id="3d9cc-112">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="3d9cc-113">Požadavky:</span><span class="sxs-lookup"><span data-stu-id="3d9cc-113">Prerequisites:</span></span>

    - <span data-ttu-id="3d9cc-114">[Python](https://www.python.org/downloads/) 3.6 nebo novější</span><span class="sxs-lookup"><span data-stu-id="3d9cc-114">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="3d9cc-115">Správce balíčků Pythonu [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="3d9cc-115">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="3d9cc-116">Sada .NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="3d9cc-116">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="3d9cc-117">Nainstalujte `qsharp` – balíček Pythonu, který umožňuje spolupráci mezi Q# a Pythonem.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-117">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="3d9cc-118">Nainstalujte IQ# – jádro primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a spouštění operací v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-118">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="3d9cc-119">Pokud se během kroku `dotnet iqsharp install` zobrazí chyba, otevřete nové okno terminálu a zkuste to znovu.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-119">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="3d9cc-120">Pokud to pořád nefunguje, zkuste najít nainstalovaný nástroj `dotnet-iqsharp` (ve Windows `dotnet-iqsharp.exe`) a spusťte:</span><span class="sxs-lookup"><span data-stu-id="3d9cc-120">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="3d9cc-121">kde `/path/to/dotnet-iqsharp` nahraďte absolutní cestou k nástroji `dotnet-iqsharp` v systému souborů.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-121">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="3d9cc-122">Obvykle bude ve složce `.dotnet/tools` ve vašem uživatelském profilu.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-122">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="3d9cc-123">A to je vše!</span><span class="sxs-lookup"><span data-stu-id="3d9cc-123">That's it!</span></span> <span data-ttu-id="3d9cc-124">Nyní máte k dispozici balíček Pythonu `qsharp` i jádro IQ# pro Jupyter, které poskytuje základní funkce pro kompilaci a spouštění operací Q# z Pythonu a umožňuje používat aplikace Jupyter Notebook s podporou Q#.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-124">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provides the core functionality for compiling and executing Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="3d9cc-125">Volba prostředí IDE</span><span class="sxs-lookup"><span data-stu-id="3d9cc-125">Choose your IDE</span></span>

<span data-ttu-id="3d9cc-126">I když Q# s Pythonem můžete použít v jakémkoli integrovaném vývojovém prostředí, důrazně doporučujeme pro vaše aplikace v Q# a Pythonu používat rozhraní IDE Visual Studio Code (VS Code).</span><span class="sxs-lookup"><span data-stu-id="3d9cc-126">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="3d9cc-127">Pomocí rozšíření QDK Visual Studio Code získáte přístup k rozsáhlejším funkcím, jako jsou například upozornění, zvýrazňování syntaxe, šablony projektů a další.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-127">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="3d9cc-128">Pokud chcete použít VS Code:</span><span class="sxs-lookup"><span data-stu-id="3d9cc-128">If you would like to use VS Code:</span></span>

- <span data-ttu-id="3d9cc-129">Nainstalujte [VS Code](https://code.visualstudio.com/download) (Windows, Linux a Mac).</span><span class="sxs-lookup"><span data-stu-id="3d9cc-129">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="3d9cc-130">Nainstalujte [rozšíření QDK pro VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="3d9cc-130">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="3d9cc-131">Pokud chcete použít jiný editor, výše uvedené pokyny se nastavily.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-131">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-no-locq-program"></a><span data-ttu-id="3d9cc-132">Vytvoření prvního programu v jazyce Q#</span><span class="sxs-lookup"><span data-stu-id="3d9cc-132">Write your first Q# program</span></span>

<span data-ttu-id="3d9cc-133">Teď jste připravení ověřit instalaci balíčku Pythonu `qsharp` napsáním a spuštěním jednoduchého programu v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-133">Now you are ready to verify your `qsharp` Python package installation by writing and executing a simple Q# program.</span></span>

1. <span data-ttu-id="3d9cc-134">Vytvořte minimální operaci v jazyce Q# tím, že vytvoříte soubor s názvem `Operation.qs` a do něj přidáte následující kód:</span><span class="sxs-lookup"><span data-stu-id="3d9cc-134">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="3d9cc-135">Ve stejné složce, kde je soubor `Operation.qs`, vytvořte program v Pythonu s názvem `host.py` pro simulování operace Q# v `SampleQuantumRandomNumberGenerator()`:</span><span class="sxs-lookup"><span data-stu-id="3d9cc-135">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. <span data-ttu-id="3d9cc-136">Z prostředí, které jste vytvořili během instalace (tj. prostředí conda nebo Python, kde jste nainstalovali `qsharp`), spusťte program:</span><span class="sxs-lookup"><span data-stu-id="3d9cc-136">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="3d9cc-137">Měl by se zobrazit výsledek vyvolané operace.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-137">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="3d9cc-138">V tomto případě, kdy vaše operace generuje náhodný výsledek, se na obrazovce zobrazí buď `0`, nebo `1`.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-138">In this case, because your operation generates a random result, you will see either `0` or `1` printed on the screen.</span></span> <span data-ttu-id="3d9cc-139">Pokud program spouštíte opakovaně, měli by se oba výsledky zobrazovat přibližně stejně často.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-139">If you execute the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> * <span data-ttu-id="3d9cc-140">Kód Pythonu je běžný program v Pythonu.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-140">The Python code is just a normal Python program.</span></span> <span data-ttu-id="3d9cc-141">K psaní programu Pythonu a volání operací Q# můžete použít libovolné prostředí Pythonu, včetně aplikací Jupyter Notebook založených na Pythonu.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-141">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="3d9cc-142">Program v Pythonu může importovat operace Q# z libovolného souboru .qs umístěného ve stejné složce jako samotný kód Pythonu.</span><span class="sxs-lookup"><span data-stu-id="3d9cc-142">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3d9cc-143">Další kroky</span><span class="sxs-lookup"><span data-stu-id="3d9cc-143">Next steps</span></span>

<span data-ttu-id="3d9cc-144">Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete podle tohoto kurzu napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="3d9cc-144">Now that you have installed the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
