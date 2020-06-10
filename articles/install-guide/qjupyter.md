---
title: Vývoj s využitím poznámkových bloků Jupyter v Q#
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b80d95a160b5f46c1132d3428ba32ad6dcd5656e
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630337"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="d364d-102">Vývoj s využitím poznámkových bloků Jupyter v Q#</span><span class="sxs-lookup"><span data-stu-id="d364d-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="d364d-103">Nainstalujte QDK pro vývoj operací Q # v poznámkových blocích Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="d364d-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="d364d-104">Jupyter poznámkové bloky umožňují místní provádění kódu společně s pokyny, poznámkami a dalšími obsahy.</span><span class="sxs-lookup"><span data-stu-id="d364d-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="d364d-105">Toto prostředí je ideální pro psaní kódu Q # s vloženými vysvětleními nebo s využitím výpočetních interaktivních kurzů.</span><span class="sxs-lookup"><span data-stu-id="d364d-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="d364d-106">Podívejte se, co všechno k vytváření vlastních poznámkových bloků v Q# potřebujete.</span><span class="sxs-lookup"><span data-stu-id="d364d-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="d364d-107">IQ# (anglicky se vyslovuje i-q-sharp) je rozšíření sady .NET Core SDK primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a simulaci operací v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="d364d-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="d364d-108">V poznámkových blocích Q # Jupyter můžete spustit pouze kód Q # a operace nelze volat z externích hostitelských programů (například souborů Python nebo C#).</span><span class="sxs-lookup"><span data-stu-id="d364d-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="d364d-109">Toto prostředí není vhodné, pokud je vaším cílem kombinování externího programu klasického hostitele s programem.</span><span class="sxs-lookup"><span data-stu-id="d364d-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="d364d-110">Požadavky</span><span class="sxs-lookup"><span data-stu-id="d364d-110">Prerequisites</span></span>

    - <span data-ttu-id="d364d-111">[Python](https://www.python.org/downloads/) 3.6 nebo novější</span><span class="sxs-lookup"><span data-stu-id="d364d-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="d364d-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="d364d-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="d364d-113">.NET Core SDK 3,1</span><span class="sxs-lookup"><span data-stu-id="d364d-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="d364d-114">Nainstalujte balíček `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="d364d-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="d364d-115">Pokud se během kroku zobrazí chyba `dotnet iqsharp install` , otevřete nové okno terminálu a zkuste to znovu.</span><span class="sxs-lookup"><span data-stu-id="d364d-115">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="d364d-116">Pokud to pořád nefunguje, zkuste vyhledat nainstalovaný `dotnet-iqsharp` Nástroj (ve Windows, `dotnet-iqsharp.exe` ) a spusťte:</span><span class="sxs-lookup"><span data-stu-id="d364d-116">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="d364d-117">kde `/path/to/dotnet-iqsharp` by měla být nahrazena absolutní cestou k `dotnet-iqsharp` nástroji v systému souborů.</span><span class="sxs-lookup"><span data-stu-id="d364d-117">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="d364d-118">Obvykle se tato složka nachází `.dotnet/tools` ve složce vašeho profilu uživatele.</span><span class="sxs-lookup"><span data-stu-id="d364d-118">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>

1. <span data-ttu-id="d364d-119">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="d364d-119">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="d364d-120">Spusťte následující příkaz, kterým se spustí server poznámkového bloku:</span><span class="sxs-lookup"><span data-stu-id="d364d-120">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="d364d-121">Chcete-li otevřít Jupyter Notebook, zkopírujte a vložte adresu URL poskytnutou příkazovým řádkem do prohlížeče.</span><span class="sxs-lookup"><span data-stu-id="d364d-121">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="d364d-122">Vytvořte Jupyter Notebook s jádrem Q # a přidejte do první buňky poznámkového bloku následující kód:</span><span class="sxs-lookup"><span data-stu-id="d364d-122">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="d364d-123">Spusťte tuto buňku poznámkového bloku:</span><span class="sxs-lookup"><span data-stu-id="d364d-123">Run this cell of the notebook:</span></span>

        ![Jupyter Notebook buňka s kódem Q #](~/media/install-guide-jupyter.png)

        <span data-ttu-id="d364d-125">Ve výstupu buňky by se měl zobrazit text `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="d364d-125">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="d364d-126">Při spuštění v Jupyter Notebook se kód Q # zkompiluje a Poznámkový blok vytvoří název operací, které najde.</span><span class="sxs-lookup"><span data-stu-id="d364d-126">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="d364d-127">V nové buňce spusťte právě vytvořenou operaci (v simulátoru) pomocí `%simulate` příkazu:</span><span class="sxs-lookup"><span data-stu-id="d364d-127">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Jupyter Notebook buňka s% simulující Magic](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="d364d-129">Měla by se zobrazit zpráva vytištěná na obrazovce spolu s výsledkem operace, kterou jste vyvolali (tady vidíte prázdné řazené kolekce členů, `()` protože naše operace jednoduše vrací `Unit` typ).</span><span class="sxs-lookup"><span data-stu-id="d364d-129">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d364d-130">Další kroky</span><span class="sxs-lookup"><span data-stu-id="d364d-130">Next steps</span></span>

<span data-ttu-id="d364d-131">Teď, když jste nainstalovali QDK pro poznámkové bloky Q # Jupyter, můžete napsat a spustit [svůj první program](xref:microsoft.quantum.quickstarts.qrng) pro práci pomocí zápisu kódu Q # přímo v prostředí Jupyter notebook.</span><span class="sxs-lookup"><span data-stu-id="d364d-131">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="d364d-132">Další příklady toho, co můžete dělat s poznámkovým blokem Q # Jupyter, najdete na adrese:</span><span class="sxs-lookup"><span data-stu-id="d364d-132">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="d364d-133">[Úvod do Q # a Jupyter notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="d364d-133">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="d364d-134">Najdete tu Jupyter Notebook Q #, která ukazuje, jak v tomto prostředí použít Q #.</span><span class="sxs-lookup"><span data-stu-id="d364d-134">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="d364d-135">Ve formě [Katasch](xref:microsoft.quantum.overview.katas)poznámkových bloků Q # Jupyter, což je open source kolekce kurzů s vlastním tempem a sady cvičení programování.</span><span class="sxs-lookup"><span data-stu-id="d364d-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="d364d-136">Dobrým výchozím bodem je [katas Poznámkový blok](https://github.com/microsoft/QuantumKatas#tutorial-topics) pro počáteční hodnotu.</span><span class="sxs-lookup"><span data-stu-id="d364d-136">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="d364d-137">Katasa za sebou se zaměřuje na výuku, které vám pomohou vymezit výpočetní výkon a programování Q # ve stejnou dobu.</span><span class="sxs-lookup"><span data-stu-id="d364d-137">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="d364d-138">Jedná se o skvělý příklad toho, jaký druh obsahu můžete vytvořit pomocí poznámkových bloků Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="d364d-138">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
