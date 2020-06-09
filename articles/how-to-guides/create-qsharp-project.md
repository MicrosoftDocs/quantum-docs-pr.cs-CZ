---
title: 'Informace o tom, jak vytvořit projekt Q # pomocí QDK (pro vývoj pro všechna množství)'
description: 'Inicializujte projekt pro vývoj s využitím neQDKch a Q # ve vývojovém prostředí dle vašeho výběru.'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 8af8e3288aab731520ede984d5f89644de292385
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578207"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="de165-103">Vytvoření projektu Q # ve vývojovém prostředí</span><span class="sxs-lookup"><span data-stu-id="de165-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="de165-104">Naučte se vytvořit projekt Q # pomocí QDK.</span><span class="sxs-lookup"><span data-stu-id="de165-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="de165-105">Projekt Q # obsahuje soubory Q #, které obsahují kód doby a hostitelský program pro spouštění programu pro práci s více operačními systémy.</span><span class="sxs-lookup"><span data-stu-id="de165-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="de165-106">Můžete napsat hostitelský program v jazycích .NET, jako je C# nebo v Pythonu.</span><span class="sxs-lookup"><span data-stu-id="de165-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="de165-107">Můžete také spustit kód Q # v Jupyter Notebook pomocí jádra SWEETIQ #.</span><span class="sxs-lookup"><span data-stu-id="de165-107">You can also run Q# code in a Jupyter Notebook using the IQ# kernel.</span></span>

<span data-ttu-id="de165-108">Vyberte vývojové prostředí a jazyk z následujících částí:</span><span class="sxs-lookup"><span data-stu-id="de165-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="de165-109">Python</span><span class="sxs-lookup"><span data-stu-id="de165-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="de165-110">Aplikace Jupyter Notebook v Q#</span><span class="sxs-lookup"><span data-stu-id="de165-110">Q# Jupyter Notebooks</span></span>](#create-a-q-jupyter-notebook-project)
* [<span data-ttu-id="de165-111">C# se sadou Visual Studio</span><span class="sxs-lookup"><span data-stu-id="de165-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="de165-112">C# s VS Code</span><span class="sxs-lookup"><span data-stu-id="de165-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="de165-113">C# s příkazovým řádkem</span><span class="sxs-lookup"><span data-stu-id="de165-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="de165-114">Vytvoření projektu v Pythonu</span><span class="sxs-lookup"><span data-stu-id="de165-114">Create a Python project</span></span>

1. <span data-ttu-id="de165-115">Požadavky</span><span class="sxs-lookup"><span data-stu-id="de165-115">Pre-requisites</span></span>

     * <span data-ttu-id="de165-116">Instalace [sady pro vývoj pro](xref:microsoft.quantum.install.python) všechna tato prostředí pro Python</span><span class="sxs-lookup"><span data-stu-id="de165-116">Install the [Quantum Development Kit for Python](xref:microsoft.quantum.install.python)</span></span>

1. <span data-ttu-id="de165-117">Vytvořte složku pro váš projekt a přejděte do této složky.</span><span class="sxs-lookup"><span data-stu-id="de165-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="de165-118">Vytvořte soubor Q # s názvem `Operation.qs` a přidejte do něj svůj kód q #.</span><span class="sxs-lookup"><span data-stu-id="de165-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="de165-119">Například:</span><span class="sxs-lookup"><span data-stu-id="de165-119">For example:</span></span>

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

1. <span data-ttu-id="de165-120">Vytvořte soubor hostitele Pythonu `host.py` s názvem pro volání operace Q #.</span><span class="sxs-lookup"><span data-stu-id="de165-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="de165-121">Například:</span><span class="sxs-lookup"><span data-stu-id="de165-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="de165-122">Spusťte program:</span><span class="sxs-lookup"><span data-stu-id="de165-122">Run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="de165-123">Ověřte výstup.</span><span class="sxs-lookup"><span data-stu-id="de165-123">Verify the output.</span></span> <span data-ttu-id="de165-124">Výstupem programu by měly být následující řádky:</span><span class="sxs-lookup"><span data-stu-id="de165-124">Your program should output the following lines:</span></span>

    ```
    Hello from quantum world!
    0
    ```

<span data-ttu-id="de165-125">Nyní můžete pokračovat v vývoji programu pro práci s více.</span><span class="sxs-lookup"><span data-stu-id="de165-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-q-jupyter-notebook-project"></a><span data-ttu-id="de165-126">Vytvoření projektu Q # Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="de165-126">Create a Q# Jupyter Notebook project</span></span>

1. <span data-ttu-id="de165-127">Požadavky</span><span class="sxs-lookup"><span data-stu-id="de165-127">Pre-requisites</span></span>

    * <span data-ttu-id="de165-128">Nainstalujte si [pro Jupyter poznámkové bloky pro vývoj pro](xref:microsoft.quantum.install.jupyter) všechna ta.</span><span class="sxs-lookup"><span data-stu-id="de165-128">Install the [Quantum Development Kit for Jupyter Notebooks](xref:microsoft.quantum.install.jupyter)</span></span>

1. <span data-ttu-id="de165-129">Spusťte následující příkaz, kterým se spustí server poznámkového bloku:</span><span class="sxs-lookup"><span data-stu-id="de165-129">Run the following command to start the notebook server:</span></span>

    ```
    jupyter notebook
    ```

1. <span data-ttu-id="de165-130">Přejděte na adresu URL zobrazenou na příkazovém řádku.</span><span class="sxs-lookup"><span data-stu-id="de165-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="de165-131">Příklad: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span><span class="sxs-lookup"><span data-stu-id="de165-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="de165-132">V prohlížeči se zobrazí stránka Jupyter.</span><span class="sxs-lookup"><span data-stu-id="de165-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="de165-133">Na kartě **soubory** vyberte **Nový**  >  **Q #** a vytvořte Jupyter notebook s jádrem Q #.</span><span class="sxs-lookup"><span data-stu-id="de165-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter Notebook with a Q# kernel.</span></span> <span data-ttu-id="de165-134">Do první buňky poznámkového bloku přidejte následující kód:</span><span class="sxs-lookup"><span data-stu-id="de165-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="de165-135">Vyberte **buňky**  >  pro**spuštění** poznámkového bloku.</span><span class="sxs-lookup"><span data-stu-id="de165-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="de165-136">`SayHello`brzy se zobrazí ve výstupu buňky:</span><span class="sxs-lookup"><span data-stu-id="de165-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Jupyter Notebook buňka s kódem Q #](~/media/install-guide-jupyter.png)

    <span data-ttu-id="de165-138">Při spuštění v poznámkových blocích Jupyter se zkompiluje kód Q # a výstup poznámkového bloku vytvoří název operací, které najde.</span><span class="sxs-lookup"><span data-stu-id="de165-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="de165-139">V nové buňce simulujte spuštění právě vytvořené operace v kvantovém počítači, a to pomocí příkazu magic `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="de165-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![Jupyter Notebook buňka s% simulující Magic](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="de165-141">Měla by se zobrazit zpráva na obrazovce spolu s výsledkem operace, kterou jste vyvolali (v tomto případě prázdným).</span><span class="sxs-lookup"><span data-stu-id="de165-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="de165-142">Nyní můžete přidat další operace Q #, abyste mohli pokračovat ve vývoji vašeho vlastního navýšení.</span><span class="sxs-lookup"><span data-stu-id="de165-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="de165-143">Vytvoření projektu v jazyce C# ve Windows pomocí sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="de165-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="de165-144">Požadavky</span><span class="sxs-lookup"><span data-stu-id="de165-144">Pre-requisites</span></span>

    * <span data-ttu-id="de165-145">Instalace [rozšíření pro vývojovou sadu pro Visual Studio](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="de165-145">Install the [Quantum Development Kit extension for Visual Studio](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="de165-146">Vytvořte novou aplikaci v jazyku Q#.</span><span class="sxs-lookup"><span data-stu-id="de165-146">Create a new Q# application</span></span>

    * <span data-ttu-id="de165-147">Přejít na **soubor**  ->  **Nový**  ->  **projekt**</span><span class="sxs-lookup"><span data-stu-id="de165-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="de165-148">Do vyhledávacího pole zadejte `Q#`.</span><span class="sxs-lookup"><span data-stu-id="de165-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="de165-149">Vyberte **Aplikace Q#**.</span><span class="sxs-lookup"><span data-stu-id="de165-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="de165-150">Vybrat **Další**</span><span class="sxs-lookup"><span data-stu-id="de165-150">Select **Next**</span></span>
    * <span data-ttu-id="de165-151">Vyberte název a umístění aplikace.</span><span class="sxs-lookup"><span data-stu-id="de165-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="de165-152">Vyberte **vytvořit** .</span><span class="sxs-lookup"><span data-stu-id="de165-152">Select **Create**</span></span>

1. <span data-ttu-id="de165-153">Prozkoumejte projekt.</span><span class="sxs-lookup"><span data-stu-id="de165-153">Inspect the project</span></span>

    <span data-ttu-id="de165-154">Měli byste zjistit, že byly vytvořeny dva soubory: `Driver.cs`, což je hostitelská aplikace C#, a `Operation.qs`, což je program v jazyku Q#, který definuje jednoduchou operaci zobrazení zprávy na konzole.</span><span class="sxs-lookup"><span data-stu-id="de165-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="de165-155">Spuštění aplikace</span><span class="sxs-lookup"><span data-stu-id="de165-155">Run the application</span></span>

    * <span data-ttu-id="de165-156">Vyberte **ladit**  ->  **Spustit bez ladění**</span><span class="sxs-lookup"><span data-stu-id="de165-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="de165-157">V okně konzoly by se měl zobrazit text `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="de165-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="de165-158">Nyní můžete pokračovat ve vývoji vašeho vlastního využití pomocí sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="de165-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="de165-159">Pokud řešení sady Visual Studio obsahuje více projektů, musí se všechny projekty obsažené v řešení nacházet ve stejné složce jako řešení nebo v jedné z jejích podsložek.</span><span class="sxs-lookup"><span data-stu-id="de165-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="de165-160">Vytvoření projektu v jazyce C# pomocí VS Code</span><span class="sxs-lookup"><span data-stu-id="de165-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="de165-161">Požadavky</span><span class="sxs-lookup"><span data-stu-id="de165-161">Pre-requisites</span></span>

    * <span data-ttu-id="de165-162">Instalace [rozšíření pro vývojovou sadu pro vs Code](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="de165-162">Install the [Quantum Development Kit extension for VS Code](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="de165-163">Vytvořte nový projekt:</span><span class="sxs-lookup"><span data-stu-id="de165-163">Create a new project:</span></span>

    * <span data-ttu-id="de165-164">Přejít na **View**  ->  **paletu příkazů** zobrazení</span><span class="sxs-lookup"><span data-stu-id="de165-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="de165-165">Vyberte **Q #: vytvořit nový projekt.**</span><span class="sxs-lookup"><span data-stu-id="de165-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="de165-166">Vybrat **samostatnou konzolovou aplikaci**</span><span class="sxs-lookup"><span data-stu-id="de165-166">Select **Standalone console application**</span></span>
    * <span data-ttu-id="de165-167">Přejděte do umístění v systému souborů, ve kterém chcete aplikaci vytvořit.</span><span class="sxs-lookup"><span data-stu-id="de165-167">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="de165-168">Po vytvoření projektu klikněte na tlačítko **Otevřít nový projekt**.</span><span class="sxs-lookup"><span data-stu-id="de165-168">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="de165-169">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="de165-169">Run the application:</span></span>

    * <span data-ttu-id="de165-170">Přejít na **terminál**  ->  **nový terminál**</span><span class="sxs-lookup"><span data-stu-id="de165-170">Go to **Terminal** -> **New Terminal**</span></span>
    * <span data-ttu-id="de165-171">Napište`dotnet run`</span><span class="sxs-lookup"><span data-stu-id="de165-171">Enter `dotnet run`</span></span>
    * <span data-ttu-id="de165-172">V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="de165-172">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="de165-173">Nyní můžete pokračovat ve vývoji ve vaší práci pomocí Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="de165-173">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="de165-174">Rozšíření Visual Studio Code aktuálně nepodporuje pracovní prostory s více kořenovými složkami.</span><span class="sxs-lookup"><span data-stu-id="de165-174">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="de165-175">Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.</span><span class="sxs-lookup"><span data-stu-id="de165-175">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="de165-176">Vytvoření projektu v jazyce C# pomocí `dotnet` nástroje příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="de165-176">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="de165-177">Požadavky</span><span class="sxs-lookup"><span data-stu-id="de165-177">Pre-requisites</span></span>

    * <span data-ttu-id="de165-178">Instalace [sady pro vývoj pro všechna ta v příkazovém řádku](xref:microsoft.quantum.install.standalone)</span><span class="sxs-lookup"><span data-stu-id="de165-178">Install the [Quantum Development Kit for the command line](xref:microsoft.quantum.install.standalone)</span></span>

1. <span data-ttu-id="de165-179">Vytvoření nové aplikace</span><span class="sxs-lookup"><span data-stu-id="de165-179">Create a new application</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="de165-180">Přejděte do adresáře nové aplikace.</span><span class="sxs-lookup"><span data-stu-id="de165-180">Navigate to the new application directory</span></span>

    ```
    cd <project name>
    ```

    <span data-ttu-id="de165-181">Spolu se soubory projektu aplikace by se měly zobrazovat dva vytvořené soubory: soubor v jazyku Q# (`Operation.qs`) a soubor hostitele v jazyku C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="de165-181">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="de165-182">Spuštění aplikace</span><span class="sxs-lookup"><span data-stu-id="de165-182">Run the application</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="de165-183">Měl by se zobrazit následující výstup: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="de165-183">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="de165-184">Teď budete pokračovat ve vývoji ve vaší práci pomocí nástrojů příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="de165-184">You now continue your quantum development, using command line tools.</span></span>

## <a name="next-steps"></a><span data-ttu-id="de165-185">Další kroky</span><span class="sxs-lookup"><span data-stu-id="de165-185">Next steps</span></span>

<span data-ttu-id="de165-186">Teď, když jste vytvořili projekt v upřednostňovaném prostředí, můžete pokračovat ve vývoji vašeho vlastního navýšení.</span><span class="sxs-lookup"><span data-stu-id="de165-186">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
