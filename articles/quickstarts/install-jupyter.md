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
ms.openlocfilehash: b34d89ab33a4644c1dd4342949685f9bf84babd8
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771394"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a><span data-ttu-id="e1b33-103">Vývoj s využitím aplikací Jupyter Notebook s podporou Q#</span><span class="sxs-lookup"><span data-stu-id="e1b33-103">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="e1b33-104">Nainstalujte QDK pro vývoj operací Q# v aplikacích Jupyter Notebook s podporou Q#.</span><span class="sxs-lookup"><span data-stu-id="e1b33-104">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="e1b33-105">Jupyter Notebooks umožňuje místní spouštění kódu přímo z poznámkového bloku a jeho doplnění o instrukce, poznámky a další obsah.</span><span class="sxs-lookup"><span data-stu-id="e1b33-105">Jupyter Notebooks allow running code in-place alongside instructions, notes, and other content.</span></span> <span data-ttu-id="e1b33-106">Toto prostředí je ideální pro psaní kódu Q# s vloženými vysvětleními nebo pro interaktivní kurzy kvantových výpočtů.</span><span class="sxs-lookup"><span data-stu-id="e1b33-106">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="e1b33-107">Podívejte se, co všechno k vytváření vlastních poznámkových bloků v Q# potřebujete.</span><span class="sxs-lookup"><span data-stu-id="e1b33-107">Here's what you need to do to start creating your own Q# notebooks.</span></span>

## <a name="install-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="e1b33-108">Instalace jádra IQ# Jupyter</span><span class="sxs-lookup"><span data-stu-id="e1b33-108">Install the IQ# Jupyter kernel</span></span>

<span data-ttu-id="e1b33-109">IQ# (anglicky se vyslovuje i-q-sharp) je rozšíření sady .NET Core SDK primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a simulaci operací v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="e1b33-109">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="e1b33-110">Instalace pomocí prostředí conda (doporučeno)</span><span class="sxs-lookup"><span data-stu-id="e1b33-110">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="e1b33-111">Nainstalujte aplikaci [Miniconda](https://docs.conda.io/en/latest/miniconda.html) nebo [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="e1b33-111">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="e1b33-112">**Poznámka:** Vyžaduje se 64 bitová instalace.</span><span class="sxs-lookup"><span data-stu-id="e1b33-112">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="e1b33-113">Otevřete příkazový řádek aplikace Anaconda.</span><span class="sxs-lookup"><span data-stu-id="e1b33-113">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="e1b33-114">Případně pokud dáváte přednost použití PowerShellu nebo pwsh: otevřete prostředí, spusťte příkaz `conda init powershell` a pak prostředí zavřete a znovu otevřete.</span><span class="sxs-lookup"><span data-stu-id="e1b33-114">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="e1b33-115">Spuštěním následujících příkazů vytvořte a aktivujte nové prostředí conda s názvem `qsharp-env` s požadovanými balíčky (včetně Jupyter Notebook a IQ#):</span><span class="sxs-lookup"><span data-stu-id="e1b33-115">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="e1b33-116">Spusťte příkaz `python -c "import qsharp"` ze stejného terminálu, abyste ověřili instalaci a naplnili místní mezipaměť balíčků všemi požadovanými součástmi QDK.</span><span class="sxs-lookup"><span data-stu-id="e1b33-116">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-advanced"></a>[<span data-ttu-id="e1b33-117">Instalace pomocí rozhraní .NET CLI (rozšířené)</span><span class="sxs-lookup"><span data-stu-id="e1b33-117">Install using .NET CLI (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="e1b33-118">Požadavky:</span><span class="sxs-lookup"><span data-stu-id="e1b33-118">Prerequisites:</span></span>

    - <span data-ttu-id="e1b33-119">[Python](https://www.python.org/downloads/) 3.6 nebo novější</span><span class="sxs-lookup"><span data-stu-id="e1b33-119">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="e1b33-120">Poznámkový blok Jupyter</span><span class="sxs-lookup"><span data-stu-id="e1b33-120">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="e1b33-121">Sada .NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="e1b33-121">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="e1b33-122">Nainstalujte balíček `Microsoft.Quantum.IQSharp`.</span><span class="sxs-lookup"><span data-stu-id="e1b33-122">Install the `Microsoft.Quantum.IQSharp` package.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

> [!NOTE]
> <span data-ttu-id="e1b33-123">Pokud se během kroku `dotnet iqsharp install` zobrazí chyba, otevřete nové okno terminálu a zkuste to znovu.</span><span class="sxs-lookup"><span data-stu-id="e1b33-123">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
> <span data-ttu-id="e1b33-124">Pokud to pořád nefunguje, zkuste najít nainstalovaný nástroj `dotnet-iqsharp` (ve Windows `dotnet-iqsharp.exe`) a spusťte:</span><span class="sxs-lookup"><span data-stu-id="e1b33-124">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
> ```
> /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
> ```
> <span data-ttu-id="e1b33-125">kde `/path/to/dotnet-iqsharp` nahraďte absolutní cestou k nástroji `dotnet-iqsharp` v systému souborů.</span><span class="sxs-lookup"><span data-stu-id="e1b33-125">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
> <span data-ttu-id="e1b33-126">Obvykle bude ve složce `.dotnet/tools` ve vašem uživatelském profilu.</span><span class="sxs-lookup"><span data-stu-id="e1b33-126">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="e1b33-127">A to je vše!</span><span class="sxs-lookup"><span data-stu-id="e1b33-127">That's it!</span></span> <span data-ttu-id="e1b33-128">Nyní máte jádro IQ# pro Jupyter, které poskytuje základní funkce pro kompilaci a spouštění operací Q# z aplikací Jupyter Notebook s podporou Q#.</span><span class="sxs-lookup"><span data-stu-id="e1b33-128">You now have the IQ# kernel for Jupyter, which provides the core functionality for compiling and running Q# operations from Q# Jupyter Notebooks.</span></span>

## <a name="create-your-first-no-locq-notebook"></a><span data-ttu-id="e1b33-129">Vytvoření prvního poznámkového bloku v Q#</span><span class="sxs-lookup"><span data-stu-id="e1b33-129">Create your first Q# notebook</span></span>

<span data-ttu-id="e1b33-130">Teď jste připravení ověřit instalaci aplikace Jupyter Notebook s podporou Q# napsáním a spuštěním jednoduché operace v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="e1b33-130">Now you are ready to verify your Q# Jupyter Notebook installation by writing and running a simple Q# operation.</span></span>

1. <span data-ttu-id="e1b33-131">Z prostředí, které jste vytvořili během instalace (tj. buď z prostředí conda, které jste vytvořili, nebo prostředí Pythonu, do kterého jste nainstalovali Jupyter), spusťte následující příkaz, který spustí server Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="e1b33-131">From the environment you created during installation (i.e., either the conda environment you created, or the Python environment where you installed Jupyter), run the following command to start the Jupyter Notebook server:</span></span>

    ```
    jupyter notebook
    ```

    - <span data-ttu-id="e1b33-132">Pokud se Jupyter Notebook neotevřete automaticky, zkopírujte a vložte do prohlížeče adresu URL poskytnutou příkazovým řádkem.</span><span class="sxs-lookup"><span data-stu-id="e1b33-132">If the Jupyter Notebook doesn't open automatically in your browser, copy and paste the URL provided by the command line into your browser.</span></span>

1. <span data-ttu-id="e1b33-133">Zvolte **New (Nový) → Q#** a vytvořte Jupyter Notebook s použitím jádra Q#. Do první buňky poznámkového bloku přidejte následující kód:</span><span class="sxs-lookup"><span data-stu-id="e1b33-133">Choose **New → Q#** to create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. <span data-ttu-id="e1b33-134">Spusťte tuto buňku poznámkového bloku:</span><span class="sxs-lookup"><span data-stu-id="e1b33-134">Run this cell of the notebook:</span></span>

    ![Buňka aplikace Jupyter Notebook s kódem Q#](~/media/install-guide-jupyter.png)

    <span data-ttu-id="e1b33-136">Ve výstupu buňky by se měl zobrazit text `SampleQuantumRandomNumberGenerator`.</span><span class="sxs-lookup"><span data-stu-id="e1b33-136">You should see `SampleQuantumRandomNumberGenerator` in the output of the cell.</span></span> <span data-ttu-id="e1b33-137">Při spouštění v aplikacích Jupyter Notebook se kód Q# kompiluje a výstupem buňky jsou názvy všech nalezených operací.</span><span class="sxs-lookup"><span data-stu-id="e1b33-137">When running in Jupyter Notebook, the Q# code is compiled, and the cell outputs the name of any operations that it finds.</span></span>

1. <span data-ttu-id="e1b33-138">V nové buňce spusťte právě vytvořenou operaci (v simulátoru) pomocí příkazu `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="e1b33-138">In a new cell, run the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

    ![Buňka poznámkového bloku Jupyter s magic příkazem %simulate](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="e1b33-140">Měl by se zobrazit výsledek vyvolané operace.</span><span class="sxs-lookup"><span data-stu-id="e1b33-140">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="e1b33-141">V tomto případě, kdy vaše operace generuje náhodný výsledek, se na obrazovce zobrazí buď `Zero`, nebo `One`.</span><span class="sxs-lookup"><span data-stu-id="e1b33-141">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="e1b33-142">Pokud buňku spouštíte opakovaně, měli by se oba výsledky zobrazovat přibližně stejně často.</span><span class="sxs-lookup"><span data-stu-id="e1b33-142">If you run the cell repeatedly, you should see each result approximately half the time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e1b33-143">Další kroky</span><span class="sxs-lookup"><span data-stu-id="e1b33-143">Next steps</span></span>

<span data-ttu-id="e1b33-144">Teď, když jste nainstalovali QDK pro aplikace Jupyter Notebook s podporou Q#, můžete napsat a spustit svůj [první kvantový program](xref:microsoft.quantum.quickstarts.qrng) tak, že kód Q# budete psát přímo v prostředí Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="e1b33-144">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="e1b33-145">Další příklady použití aplikací Jupyter Notebook s podporou Q# najdete v těchto tématech:</span><span class="sxs-lookup"><span data-stu-id="e1b33-145">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>

- <span data-ttu-id="e1b33-146">[Úvod k Q# a aplikacím Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="e1b33-146">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="e1b33-147">V tomto článku najdete Jupyter Notebook s podporou Q#, který ukazuje další podrobnosti, jak používat jazyk Q# v prostředí Jupyter.</span><span class="sxs-lookup"><span data-stu-id="e1b33-147">There you will find a Q# Jupyter Notebook that provides more details on how to use Q# in the Jupyter environment.</span></span>
- <span data-ttu-id="e1b33-148">[Quantum Katas](xref:microsoft.quantum.overview.katas), opensourcová kolekce kurzů umožňujících postupovat vlastním tempem a sady programovacích cvičení ve formě aplikací Jupyter Notebook s podporou Q#.</span><span class="sxs-lookup"><span data-stu-id="e1b33-148">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="e1b33-149">[Poznámkové bloky kurzů Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) jsou dobrým výchozím bodem.</span><span class="sxs-lookup"><span data-stu-id="e1b33-149">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="e1b33-150">Quantum Katas se zaměřují současně na výuku základních prvků kvantových výpočtů i na programování v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="e1b33-150">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="e1b33-151">Skvělým způsobem předvádějí, jaký typ obsahu můžete pomocí aplikací Jupyter Notebook s podporou Q# vytvářet.</span><span class="sxs-lookup"><span data-stu-id="e1b33-151">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
