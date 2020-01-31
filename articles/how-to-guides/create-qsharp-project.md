---
title: 'Informace o tom, jak vytvořit projekt Q # pomocí QDK (pro vývoj pro všechna množství)'
description: 'Inicializujte projekt pro vývoj s využitím neQDKch a Q # ve vývojovém prostředí dle vašeho výběru.'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 5fa32f14291fa2070b49e4bb3b720cbf31ee614b
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819888"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="04973-103">Vytvoření projektu Q # ve vývojovém prostředí</span><span class="sxs-lookup"><span data-stu-id="04973-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="04973-104">Naučte se vytvořit projekt Q # pomocí QDK.</span><span class="sxs-lookup"><span data-stu-id="04973-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="04973-105">Projekt Q # obsahuje soubory Q #, které obsahují kód doby a hostitelský program pro spouštění programu pro práci s více operačními systémy.</span><span class="sxs-lookup"><span data-stu-id="04973-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="04973-106">Hostitelský program můžete napsat v jazycích .NET C#, jako je, nebo v Pythonu.</span><span class="sxs-lookup"><span data-stu-id="04973-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="04973-107">Můžete také spustit kód Q # v poznámkovém bloku Jupyter pomocí jádra SWEETIQ #.</span><span class="sxs-lookup"><span data-stu-id="04973-107">You can also run Q# code in a Jupyter notebook using the IQ# kernel.</span></span>

<span data-ttu-id="04973-108">Vyberte vývojové prostředí a jazyk z následujících částí:</span><span class="sxs-lookup"><span data-stu-id="04973-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="04973-109">Python</span><span class="sxs-lookup"><span data-stu-id="04973-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="04973-110">Notebooky Q # Jupyter</span><span class="sxs-lookup"><span data-stu-id="04973-110">Q# Jupyter notebooks</span></span>](#create-a-q-jupyter-notebook-project)
* [<span data-ttu-id="04973-111">C#se sadou Visual Studio</span><span class="sxs-lookup"><span data-stu-id="04973-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="04973-112">C#s VS Code</span><span class="sxs-lookup"><span data-stu-id="04973-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="04973-113">C#pomocí příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="04973-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="04973-114">Vytvoření projektu v Pythonu</span><span class="sxs-lookup"><span data-stu-id="04973-114">Create a Python project</span></span>

1. <span data-ttu-id="04973-115">Požadavky</span><span class="sxs-lookup"><span data-stu-id="04973-115">Pre-requisites</span></span>

     * <span data-ttu-id="04973-116">Instalace [sady pro vývoj pro](xref:microsoft.quantum.install.python) všechna tato prostředí pro Python</span><span class="sxs-lookup"><span data-stu-id="04973-116">Install the [Quantum Development Kit for Python](xref:microsoft.quantum.install.python)</span></span>

1. <span data-ttu-id="04973-117">Vytvořte složku pro váš projekt a přejděte do této složky.</span><span class="sxs-lookup"><span data-stu-id="04973-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="04973-118">Vytvořte soubor Q # s názvem `Operation.qs`a přidejte do něj svůj kód Q #.</span><span class="sxs-lookup"><span data-stu-id="04973-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="04973-119">Příklad:</span><span class="sxs-lookup"><span data-stu-id="04973-119">For example:</span></span>

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. <span data-ttu-id="04973-120">Vytvořte soubor hostitele Pythonu s názvem `host.py` pro volání operace Q #.</span><span class="sxs-lookup"><span data-stu-id="04973-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="04973-121">Příklad:</span><span class="sxs-lookup"><span data-stu-id="04973-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="04973-122">Spusťte program:</span><span class="sxs-lookup"><span data-stu-id="04973-122">Run the program:</span></span>

    ```bash
    python host.py
    ```

1. <span data-ttu-id="04973-123">Ověřte výstup.</span><span class="sxs-lookup"><span data-stu-id="04973-123">Verify the output.</span></span> <span data-ttu-id="04973-124">Výstupem programu by měly být následující řádky:</span><span class="sxs-lookup"><span data-stu-id="04973-124">Your program should output the following lines:</span></span>

    ```bash
    Hello from quantum world!
    0
    ```

<span data-ttu-id="04973-125">Nyní můžete pokračovat v vývoji programu pro práci s více.</span><span class="sxs-lookup"><span data-stu-id="04973-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-q-jupyter-notebook-project"></a><span data-ttu-id="04973-126">Vytvoření projektu Q # Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="04973-126">Create a Q# Jupyter Notebook project</span></span>

1. <span data-ttu-id="04973-127">Požadavky</span><span class="sxs-lookup"><span data-stu-id="04973-127">Pre-requisites</span></span>

    * <span data-ttu-id="04973-128">Nainstalujte si [pro Jupyter poznámkové bloky pro vývoj pro](xref:microsoft.quantum.install.jupyter) všechna ta.</span><span class="sxs-lookup"><span data-stu-id="04973-128">Install the [Quantum Development Kit for Jupyter notebooks](xref:microsoft.quantum.install.jupyter)</span></span>

1. <span data-ttu-id="04973-129">Spusťte následující příkaz, kterým se spustí server poznámkového bloku:</span><span class="sxs-lookup"><span data-stu-id="04973-129">Run the following command to start the notebook server:</span></span>

    ```bash
    jupyter notebook
    ```

1. <span data-ttu-id="04973-130">Přejděte na adresu URL zobrazenou na příkazovém řádku.</span><span class="sxs-lookup"><span data-stu-id="04973-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="04973-131">Příklad: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="04973-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="04973-132">V prohlížeči se zobrazí stránka Jupyter.</span><span class="sxs-lookup"><span data-stu-id="04973-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="04973-133">Na kartě **soubory** vyberte **Nový** > **Q #** a vytvořte Poznámkový blok Jupyter s jádrem Q #.</span><span class="sxs-lookup"><span data-stu-id="04973-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter notebook with a Q# kernel.</span></span> <span data-ttu-id="04973-134">Do první buňky poznámkového bloku přidejte následující kód:</span><span class="sxs-lookup"><span data-stu-id="04973-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="04973-135">Vyberte **buňku** > **Spustit buňky** pro spuštění poznámkového bloku.</span><span class="sxs-lookup"><span data-stu-id="04973-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="04973-136">`SayHello` se brzy objeví ve výstupu buňky:</span><span class="sxs-lookup"><span data-stu-id="04973-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Buňka poznámkového bloku Jupyter s využitím kódu Q#](~/media/install-guide-jupyter.png)

    <span data-ttu-id="04973-138">Při spuštění v poznámkových blocích Jupyter se zkompiluje kód Q # a výstup poznámkového bloku vytvoří název operací, které najde.</span><span class="sxs-lookup"><span data-stu-id="04973-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="04973-139">V nové buňce simulujte spuštění právě vytvořené operace v kvantovém počítači, a to pomocí příkazu magic `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="04973-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![Buňka poznámkového bloku Jupyter s využitím příkazu magic %simulate](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="04973-141">Měla by se zobrazit zpráva na obrazovce spolu s výsledkem operace, kterou jste vyvolali (v tomto případě prázdným).</span><span class="sxs-lookup"><span data-stu-id="04973-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="04973-142">Nyní můžete přidat další operace Q #, abyste mohli pokračovat ve vývoji vašeho vlastního navýšení.</span><span class="sxs-lookup"><span data-stu-id="04973-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="04973-143">Vytvoření C# projektu ve Windows pomocí sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="04973-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="04973-144">Požadavky</span><span class="sxs-lookup"><span data-stu-id="04973-144">Pre-requisites</span></span>

    * <span data-ttu-id="04973-145">Instalace [rozšíření pro vývojovou sadu pro Visual Studio](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="04973-145">Install the [Quantum Development Kit extension for Visual Studio](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="04973-146">Vytvořte novou aplikaci v jazyku Q#.</span><span class="sxs-lookup"><span data-stu-id="04973-146">Create a new Q# application</span></span>

    * <span data-ttu-id="04973-147">Přejděte do části **Soubor** -> **Nový** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="04973-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="04973-148">Do vyhledávacího pole zadejte `Q#`.</span><span class="sxs-lookup"><span data-stu-id="04973-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="04973-149">Vyberte **Aplikace Q#** .</span><span class="sxs-lookup"><span data-stu-id="04973-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="04973-150">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="04973-150">Select **Next**</span></span>
    * <span data-ttu-id="04973-151">Vyberte název a umístění aplikace.</span><span class="sxs-lookup"><span data-stu-id="04973-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="04973-152">Vyberte **Vytvořit**.</span><span class="sxs-lookup"><span data-stu-id="04973-152">Select **Create**</span></span>

1. <span data-ttu-id="04973-153">Prozkoumejte projekt.</span><span class="sxs-lookup"><span data-stu-id="04973-153">Inspect the project</span></span>

    <span data-ttu-id="04973-154">Měli byste zjistit, že byly vytvořeny dva soubory: `Driver.cs`, což je hostitelská aplikace C#, a `Operation.qs`, což je program v jazyku Q#, který definuje jednoduchou operaci zobrazení zprávy na konzole.</span><span class="sxs-lookup"><span data-stu-id="04973-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="04973-155">Spuštění aplikace</span><span class="sxs-lookup"><span data-stu-id="04973-155">Run the application</span></span>

    * <span data-ttu-id="04973-156">Vyberte **Ladit** -> **Spustit bez ladění**.</span><span class="sxs-lookup"><span data-stu-id="04973-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="04973-157">V okně konzoly by se měl zobrazit text `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="04973-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="04973-158">Nyní můžete pokračovat ve vývoji vašeho vlastního využití pomocí sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="04973-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="04973-159">Pokud řešení sady Visual Studio obsahuje více projektů, musí se všechny projekty obsažené v řešení nacházet ve stejné složce jako řešení nebo v jedné z jejích podsložek.</span><span class="sxs-lookup"><span data-stu-id="04973-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="04973-160">Vytvoření C# projektu pomocí vs Code</span><span class="sxs-lookup"><span data-stu-id="04973-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="04973-161">Požadavky</span><span class="sxs-lookup"><span data-stu-id="04973-161">Pre-requisites</span></span>

    * <span data-ttu-id="04973-162">Instalace [rozšíření pro vývojovou sadu pro vs Code](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="04973-162">Install the [Quantum Development Kit extension for VS Code](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="04973-163">Vytvořte nový projekt:</span><span class="sxs-lookup"><span data-stu-id="04973-163">Create a new project:</span></span>

    * <span data-ttu-id="04973-164">Přejděte do části **Zobrazit** -> **Paleta příkazů**.</span><span class="sxs-lookup"><span data-stu-id="04973-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="04973-165">Vyberte **Q #: vytvořit nový projekt.**</span><span class="sxs-lookup"><span data-stu-id="04973-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="04973-166">Vybrat **samostatnou konzolovou aplikaci**</span><span class="sxs-lookup"><span data-stu-id="04973-166">Select **Standalone console application**</span></span>
    * <span data-ttu-id="04973-167">Přejděte do umístění v systému souborů, ve kterém chcete aplikaci vytvořit.</span><span class="sxs-lookup"><span data-stu-id="04973-167">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="04973-168">Po vytvoření projektu klikněte na tlačítko **Otevřít nový projekt**.</span><span class="sxs-lookup"><span data-stu-id="04973-168">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="04973-169">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="04973-169">Run the application:</span></span>

    * <span data-ttu-id="04973-170">Přejít na **terminál** -> **nový terminál**</span><span class="sxs-lookup"><span data-stu-id="04973-170">Go to **Terminal** -> **New Terminal**</span></span>
    * <span data-ttu-id="04973-171">Zadejte `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="04973-171">Enter `dotnet run`</span></span>
    * <span data-ttu-id="04973-172">V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="04973-172">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="04973-173">Nyní můžete pokračovat ve vývoji ve vaší práci pomocí Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="04973-173">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="04973-174">Rozšíření Visual Studio Code aktuálně nepodporuje pracovní prostory s více kořenovými složkami.</span><span class="sxs-lookup"><span data-stu-id="04973-174">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="04973-175">Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.</span><span class="sxs-lookup"><span data-stu-id="04973-175">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="04973-176">Vytvoření C# projektu pomocí `dotnet` nástroje příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="04973-176">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="04973-177">Požadavky</span><span class="sxs-lookup"><span data-stu-id="04973-177">Pre-requisites</span></span>

    * <span data-ttu-id="04973-178">Instalace [sady pro vývoj pro všechna ta v příkazovém řádku](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="04973-178">Install the [Quantum Development Kit for the Command Line](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="04973-179">Vytvoření nové aplikace</span><span class="sxs-lookup"><span data-stu-id="04973-179">Create a new application</span></span>

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="04973-180">Přejděte do adresáře nové aplikace.</span><span class="sxs-lookup"><span data-stu-id="04973-180">Navigate to the new application directory</span></span>

    ```bash
    cd <project name>
    ```

    <span data-ttu-id="04973-181">Spolu se soubory projektu aplikace by se měly zobrazovat dva vytvořené soubory: soubor v jazyku Q# (`Operation.qs`) a soubor hostitele v jazyku C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="04973-181">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="04973-182">Spuštění aplikace</span><span class="sxs-lookup"><span data-stu-id="04973-182">Run the application</span></span>

    ```bash
    dotnet run
    ```

    <span data-ttu-id="04973-183">Měl by se zobrazit následující výstup: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="04973-183">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="04973-184">Teď budete pokračovat ve vývoji ve vaší práci pomocí nástrojů příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="04973-184">You now continue your quantum development, using command line tools.</span></span>

## <a name="whats-next"></a><span data-ttu-id="04973-185">A co dál?</span><span class="sxs-lookup"><span data-stu-id="04973-185">What's next?</span></span>

<span data-ttu-id="04973-186">Teď, když jste vytvořili projekt v upřednostňovaném prostředí, můžete pokračovat ve vývoji vašeho vlastního navýšení.</span><span class="sxs-lookup"><span data-stu-id="04973-186">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
