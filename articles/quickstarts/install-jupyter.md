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
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="a49b3-102">Vývoj v Q# a Jupyter Notebooks</span><span class="sxs-lookup"><span data-stu-id="a49b3-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="a49b3-103">Nainstalujte QDK pro vývoj operací Q# v Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="a49b3-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="a49b3-104">Jupyter Notebooks umožňuje místní spouštění kódu přímo z poznámkového bloku a jeho doplnění o instrukce, poznámky a další obsah.</span><span class="sxs-lookup"><span data-stu-id="a49b3-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="a49b3-105">Toto prostředí je ideální pro psaní kódu Q# s vloženými vysvětleními nebo pro interaktivní kurzy kvantových výpočtů.</span><span class="sxs-lookup"><span data-stu-id="a49b3-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="a49b3-106">Podívejte se, co všechno k vytváření vlastních poznámkových bloků v Q# potřebujete.</span><span class="sxs-lookup"><span data-stu-id="a49b3-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="a49b3-107">IQ# (anglicky se vyslovuje i-q-sharp) je rozšíření sady .NET Core SDK primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a simulaci operací v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="a49b3-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="a49b3-108">V poznámkových blocích Jupyter s Q# můžete spouštět pouze kód Q# a operace nelze volat z externích hostitelských programů (např. souborů Python nebo C#).</span><span class="sxs-lookup"><span data-stu-id="a49b3-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="a49b3-109">Toto prostředí není vhodné, pokud je vaším cílem kombinování externího klasického hostitelského programu s programem kvantovým.</span><span class="sxs-lookup"><span data-stu-id="a49b3-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="a49b3-110">Požadavky</span><span class="sxs-lookup"><span data-stu-id="a49b3-110">Prerequisites</span></span>

    - <span data-ttu-id="a49b3-111">[Python](https://www.python.org/downloads/) 3.6 nebo novější</span><span class="sxs-lookup"><span data-stu-id="a49b3-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="a49b3-112">Poznámkový blok Jupyter</span><span class="sxs-lookup"><span data-stu-id="a49b3-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="a49b3-113">Sada .NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="a49b3-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="a49b3-114">Nainstalujte balíček `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="a49b3-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="a49b3-115">Pokud se během kroku `dotnet iqsharp install` zobrazí chyba, otevřete nové okno terminálu a zkuste to znovu.</span><span class="sxs-lookup"><span data-stu-id="a49b3-115">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="a49b3-116">Pokud to pořád nefunguje, zkuste najít nainstalovaný nástroj `dotnet-iqsharp` (ve Windows `dotnet-iqsharp.exe`) a spusťte:</span><span class="sxs-lookup"><span data-stu-id="a49b3-116">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="a49b3-117">kde `/path/to/dotnet-iqsharp` nahraďte absolutní cestou k nástroji `dotnet-iqsharp` v systému souborů.</span><span class="sxs-lookup"><span data-stu-id="a49b3-117">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="a49b3-118">Obvykle bude ve složce `.dotnet/tools` ve vašem uživatelském profilu.</span><span class="sxs-lookup"><span data-stu-id="a49b3-118">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>

1. <span data-ttu-id="a49b3-119">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="a49b3-119">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="a49b3-120">Spusťte následující příkaz, kterým se spustí server poznámkového bloku:</span><span class="sxs-lookup"><span data-stu-id="a49b3-120">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="a49b3-121">Jupyter Notebook otevřete tak, že zkopírujete a vložíte do prohlížeče adresu URL poskytnutou příkazovým řádkem.</span><span class="sxs-lookup"><span data-stu-id="a49b3-121">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="a49b3-122">Vytvořte poznámkový blok Jupyter s použitím jádra Q# a do první buňky poznámkového bloku přidejte následující kód:</span><span class="sxs-lookup"><span data-stu-id="a49b3-122">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="a49b3-123">Spusťte tuto buňku poznámkového bloku:</span><span class="sxs-lookup"><span data-stu-id="a49b3-123">Run this cell of the notebook:</span></span>

        ![Buňka poznámkového bloku Jupyter s kódem Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="a49b3-125">Ve výstupu buňky by se měl zobrazit text `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="a49b3-125">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="a49b3-126">Při spouštění v poznámkových blocích Jupyter se kód Q# kompiluje a výstupem poznámkového bloku jsou názvy nalezených operací.</span><span class="sxs-lookup"><span data-stu-id="a49b3-126">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="a49b3-127">V nové buňce spusťte právě vytvořenou operaci (v simulátoru) pomocí příkazu `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="a49b3-127">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Buňka poznámkového bloku Jupyter s magic příkazem %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="a49b3-129">Na obrazovce by se měla zobrazit zpráva spolu s výsledkem vyvolané operace (v tomto případě uvidíme prázdný tuplet `()`, protože naše operace jednoduše vrací typ `Unit`).</span><span class="sxs-lookup"><span data-stu-id="a49b3-129">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a49b3-130">Další kroky</span><span class="sxs-lookup"><span data-stu-id="a49b3-130">Next steps</span></span>

<span data-ttu-id="a49b3-131">Teď, když jste nainstalovali QDK pro Q# v Jupyter Notebooks, můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng) v jazyce Q# tak, že kód Q# budete psát přímo v prostředí Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="a49b3-131">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="a49b3-132">Další příklady použití jazyka Q# v prostředí Jupyter Notebooks najdete v těchto tématech:</span><span class="sxs-lookup"><span data-stu-id="a49b3-132">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="a49b3-133">[Úvod do Q# a Jupyter Notebooks](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="a49b3-133">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="a49b3-134">V tomto článku najdete poznámkový blok Jupyter s kódem Q#, který ukazuje, jak jazyk Q# v tomto prostředí používat.</span><span class="sxs-lookup"><span data-stu-id="a49b3-134">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="a49b3-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), open source sbírka kurzů s vlastním tempem a sady programovacích cvičení ve formě poznámkových bloků Jupyter s kódem Q#.</span><span class="sxs-lookup"><span data-stu-id="a49b3-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="a49b3-136">[Poznámkové bloky kurzů Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) jsou dobrým výchozím bodem.</span><span class="sxs-lookup"><span data-stu-id="a49b3-136">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="a49b3-137">Quantum Katas se zaměřují současně na výuku základních prvků kvantových výpočtů i na programování v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="a49b3-137">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="a49b3-138">Skvělým způsobem předvádějí, jaký typ obsahu můžete pomocí poznámkových bloků Jupyter s kódem Q# vytvářet.</span><span class="sxs-lookup"><span data-stu-id="a49b3-138">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
