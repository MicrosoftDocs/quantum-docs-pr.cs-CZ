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
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="b56e9-102">Vývoj v Q# a Jupyter Notebooks</span><span class="sxs-lookup"><span data-stu-id="b56e9-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="b56e9-103">Nainstalujte QDK pro vývoj operací Q# v Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="b56e9-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="b56e9-104">Jupyter Notebooks umožňuje místní spouštění kódu přímo z poznámkového bloku a jeho doplnění o instrukce, poznámky a další obsah.</span><span class="sxs-lookup"><span data-stu-id="b56e9-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="b56e9-105">Toto prostředí je ideální pro psaní kódu Q# s vloženými vysvětleními nebo pro interaktivní kurzy kvantových výpočtů.</span><span class="sxs-lookup"><span data-stu-id="b56e9-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="b56e9-106">Podívejte se, co všechno k vytváření vlastních poznámkových bloků v Q# potřebujete.</span><span class="sxs-lookup"><span data-stu-id="b56e9-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

> [!NOTE]
> * <span data-ttu-id="b56e9-107">V poznámkových blocích Jupyter s kódem Q# můžete spouštět pouze kód Q# a operace nelze volat z externích hostitelských programů (např. souborů Python nebo C#).</span><span class="sxs-lookup"><span data-stu-id="b56e9-107">In Q# Jupyter Notebooks, you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="b56e9-108">Toto prostředí není vhodné, pokud je vaším cílem kombinování externího klasického hostitelského programu s programem kvantovým.</span><span class="sxs-lookup"><span data-stu-id="b56e9-108">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

## <a name="install-the-iq-jupyter-kernel"></a><span data-ttu-id="b56e9-109">Instalace jádra IQ# Jupyter</span><span class="sxs-lookup"><span data-stu-id="b56e9-109">Install the IQ# Jupyter kernel</span></span>

<span data-ttu-id="b56e9-110">IQ# (anglicky se vyslovuje i-q-sharp) je rozšíření sady .NET Core SDK primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a simulaci operací v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="b56e9-110">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="b56e9-111">Instalace pomocí prostředí conda (doporučeno)</span><span class="sxs-lookup"><span data-stu-id="b56e9-111">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="b56e9-112">Nainstalujte aplikaci [Miniconda](https://docs.conda.io/en/latest/miniconda.html) nebo [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="b56e9-112">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="b56e9-113">**Poznámka:** Vyžaduje se 64 bitová instalace.</span><span class="sxs-lookup"><span data-stu-id="b56e9-113">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="b56e9-114">Otevřete příkazový řádek aplikace Anaconda.</span><span class="sxs-lookup"><span data-stu-id="b56e9-114">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="b56e9-115">Případně pokud dáváte přednost použití PowerShellu nebo pwsh: otevřete prostředí, spusťte příkaz `conda init powershell` a pak prostředí zavřete a znovu otevřete.</span><span class="sxs-lookup"><span data-stu-id="b56e9-115">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="b56e9-116">Vytvořte a aktivujte nové prostředí conda s názvem `qsharp-env` s požadovanými balíčky (včetně Jupyter Notebook a IQ#) spuštěním následujících příkazů:</span><span class="sxs-lookup"><span data-stu-id="b56e9-116">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="b56e9-117">Spusťte příkaz `python -c "import qsharp"` ze stejného terminálu, abyste ověřili instalaci a naplnili místní mezipaměť balíčků všemi požadovanými součástmi QDK.</span><span class="sxs-lookup"><span data-stu-id="b56e9-117">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-advanced"></a>[<span data-ttu-id="b56e9-118">Instalace pomocí rozhraní .NET CLI (rozšířené)</span><span class="sxs-lookup"><span data-stu-id="b56e9-118">Install using .NET CLI (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="b56e9-119">Požadavky:</span><span class="sxs-lookup"><span data-stu-id="b56e9-119">Prerequisites:</span></span>

    - <span data-ttu-id="b56e9-120">[Python](https://www.python.org/downloads/) 3.6 nebo novější</span><span class="sxs-lookup"><span data-stu-id="b56e9-120">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="b56e9-121">Poznámkový blok Jupyter</span><span class="sxs-lookup"><span data-stu-id="b56e9-121">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="b56e9-122">Sada .NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="b56e9-122">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="b56e9-123">Nainstalujte balíček `Microsoft.Quantum.IQSharp`.</span><span class="sxs-lookup"><span data-stu-id="b56e9-123">Install the `Microsoft.Quantum.IQSharp` package.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="b56e9-124">Pokud se během kroku `dotnet iqsharp install` zobrazí chyba, otevřete nové okno terminálu a zkuste to znovu.</span><span class="sxs-lookup"><span data-stu-id="b56e9-124">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="b56e9-125">Pokud to pořád nefunguje, zkuste najít nainstalovaný nástroj `dotnet-iqsharp` (ve Windows `dotnet-iqsharp.exe`) a spusťte:</span><span class="sxs-lookup"><span data-stu-id="b56e9-125">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="b56e9-126">kde `/path/to/dotnet-iqsharp` nahraďte absolutní cestou k nástroji `dotnet-iqsharp` v systému souborů.</span><span class="sxs-lookup"><span data-stu-id="b56e9-126">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="b56e9-127">Obvykle bude ve složce `.dotnet/tools` ve vašem uživatelském profilu.</span><span class="sxs-lookup"><span data-stu-id="b56e9-127">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="b56e9-128">A to je vše!</span><span class="sxs-lookup"><span data-stu-id="b56e9-128">That's it!</span></span> <span data-ttu-id="b56e9-129">Nyní máte jádro IQ# pro Jupyter, které poskytuje základní funkce pro kompilaci a provádění operací Q# z poznámkových bloků Jupyter s kódem Q#.</span><span class="sxs-lookup"><span data-stu-id="b56e9-129">You now have the IQ# kernel for Jupyter, which provides the core functionality for compiling and executing Q# operations from Q# Jupyter Notebooks.</span></span>

## <a name="create-your-first-q-notebook"></a><span data-ttu-id="b56e9-130">Vytvoření prvního poznámkového bloku Q#</span><span class="sxs-lookup"><span data-stu-id="b56e9-130">Create your first Q# notebook</span></span>

<span data-ttu-id="b56e9-131">Teď jste připravení ověřit instalaci Q# Jupyter Notebook napsáním a spuštěním jednoduché operace v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="b56e9-131">Now you are ready to verify your Q# Jupyter Notebook installation by writing and executing a simple Q# operation.</span></span>

1. <span data-ttu-id="b56e9-132">Z prostředí, které jste vytvořili během instalace (tj. buď z prostředí conda, které jste vytvořili, nebo prostředí Pythonu, do kterého jste nainstalovali Jupyter), spusťte následující příkaz, který spustí server Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="b56e9-132">From the environment you created during installation (i.e., either the conda environment you created, or the Python environment where you installed Jupyter), run the following command to start the Jupyter Notebook server:</span></span>

    ```
    jupyter notebook
    ```

    - <span data-ttu-id="b56e9-133">Pokud se Jupyter Notebook neotevřete automaticky, zkopírujte a vložte do prohlížeče adresu URL poskytnutou příkazovým řádkem.</span><span class="sxs-lookup"><span data-stu-id="b56e9-133">If the Jupyter Notebook doesn't open automatically in your browser, copy and paste the URL provided by the command line into your browser.</span></span>

1. <span data-ttu-id="b56e9-134">Zvolte New (Nový) → Q# a vytvořte poznámkový blok Jupyter s použitím jádra Q#. Do první buňky poznámkového bloku přidejte následující kód:</span><span class="sxs-lookup"><span data-stu-id="b56e9-134">Choose "New" → "Q#" to create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. <span data-ttu-id="b56e9-135">Spusťte tuto buňku poznámkového bloku:</span><span class="sxs-lookup"><span data-stu-id="b56e9-135">Run this cell of the notebook:</span></span>

    ![Buňka poznámkového bloku Jupyter s kódem Q#](~/media/install-guide-jupyter.png)

    <span data-ttu-id="b56e9-137">Ve výstupu buňky by se měl zobrazit text `SampleQuantumRandomNumberGenerator`.</span><span class="sxs-lookup"><span data-stu-id="b56e9-137">You should see `SampleQuantumRandomNumberGenerator` in the output of the cell.</span></span> <span data-ttu-id="b56e9-138">Při spouštění v poznámkových blocích Jupyter se kód Q# kompiluje a výstupem buňky jsou názvy všech nalezených operací.</span><span class="sxs-lookup"><span data-stu-id="b56e9-138">When running in Jupyter Notebook, the Q# code is compiled, and the cell outputs the name of any operations that it finds.</span></span>

1. <span data-ttu-id="b56e9-139">V nové buňce spusťte právě vytvořenou operaci (v simulátoru) pomocí příkazu `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="b56e9-139">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

    ![Buňka poznámkového bloku Jupyter s magic příkazem %simulate](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="b56e9-141">Měl by se zobrazit výsledek vyvolané operace.</span><span class="sxs-lookup"><span data-stu-id="b56e9-141">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="b56e9-142">V tomto případě, kdy vaše operace generuje náhodný výsledek, se na obrazovce zobrazí buď `Zero`, nebo `One`.</span><span class="sxs-lookup"><span data-stu-id="b56e9-142">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="b56e9-143">Pokud buňku spouštíte opakovaně, měli by se oba výsledky zobrazovat přibližně stejně často.</span><span class="sxs-lookup"><span data-stu-id="b56e9-143">If you execute the cell repeatedly, you should see each result approximately half the time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b56e9-144">Další kroky</span><span class="sxs-lookup"><span data-stu-id="b56e9-144">Next steps</span></span>

<span data-ttu-id="b56e9-145">Teď, když jste nainstalovali QDK pro poznámkové bloky Jupyter s kódem Q#, můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng) v jazyce Q# tak, že kód Q# budete psát přímo v prostředí Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="b56e9-145">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="b56e9-146">Další příklady použití jazyka Q# v prostředí Jupyter Notebooks najdete v těchto tématech:</span><span class="sxs-lookup"><span data-stu-id="b56e9-146">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>

- <span data-ttu-id="b56e9-147">[Úvod do Q# a Jupyter Notebooks](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="b56e9-147">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="b56e9-148">V tomto článku najdete poznámkový blok Jupyter s kódem Q#, který ukazuje další podrobnosti, jak používat jazyk Q# v prostředí Jupyter.</span><span class="sxs-lookup"><span data-stu-id="b56e9-148">There you will find a Q# Jupyter Notebook that provides more details on how to use Q# in the Jupyter environment.</span></span>
- <span data-ttu-id="b56e9-149">[Quantum Katas](xref:microsoft.quantum.overview.katas), open source sbírka kurzů s vlastním tempem a sady programovacích cvičení ve formě poznámkových bloků Jupyter s kódem Q#.</span><span class="sxs-lookup"><span data-stu-id="b56e9-149">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="b56e9-150">[Poznámkové bloky kurzů Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) jsou dobrým výchozím bodem.</span><span class="sxs-lookup"><span data-stu-id="b56e9-150">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="b56e9-151">Quantum Katas se zaměřují současně na výuku základních prvků kvantových výpočtů i na programování v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="b56e9-151">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="b56e9-152">Skvělým způsobem předvádějí, jaký typ obsahu můžete pomocí poznámkových bloků Jupyter s kódem Q# vytvářet.</span><span class="sxs-lookup"><span data-stu-id="b56e9-152">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
