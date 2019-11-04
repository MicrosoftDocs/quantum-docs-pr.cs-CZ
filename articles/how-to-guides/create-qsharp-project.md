---
title: 'Informace o tom, jak vytvořit projekt Q # pomocí QDK (pro vývoj pro všechna množství)'
description: 'Inicializujte projekt pro vývoj s využitím neQDKch a Q # ve vývojovém prostředí dle vašeho výběru.'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: b4bec5e7a174b7e2d588331dd2093c7b23a728b0
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444170"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="f6756-103">Vytvoření projektu Q # ve vývojovém prostředí</span><span class="sxs-lookup"><span data-stu-id="f6756-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="f6756-104">Naučte se vytvořit projekt Q # pomocí QDK.</span><span class="sxs-lookup"><span data-stu-id="f6756-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="f6756-105">Projekt Q # obsahuje soubory Q #, které obsahují kód doby a hostitelský program pro spouštění programu pro práci s více operačními systémy.</span><span class="sxs-lookup"><span data-stu-id="f6756-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="f6756-106">Hostitelský program můžete napsat v jazycích .NET C#, jako je, nebo v Pythonu.</span><span class="sxs-lookup"><span data-stu-id="f6756-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="f6756-107">Můžete také spustit kód Q # v poznámkovém bloku Jupyter pomocí jádra SWEETIQ #.</span><span class="sxs-lookup"><span data-stu-id="f6756-107">You can also run Q# code in a Jupyter notebook using the IQ# kernel.</span></span>

<span data-ttu-id="f6756-108">Vyberte vývojové prostředí a jazyk z následujících částí:</span><span class="sxs-lookup"><span data-stu-id="f6756-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="f6756-109">Python</span><span class="sxs-lookup"><span data-stu-id="f6756-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="f6756-110">Jupyter poznámkové bloky</span><span class="sxs-lookup"><span data-stu-id="f6756-110">Jupyter notebooks</span></span>](#create-a-jupyter-notebook-project)
* [<span data-ttu-id="f6756-111">C#se sadou Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f6756-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="f6756-112">C#s VS Code</span><span class="sxs-lookup"><span data-stu-id="f6756-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="f6756-113">C#pomocí příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="f6756-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="f6756-114">Vytvoření projektu v Pythonu</span><span class="sxs-lookup"><span data-stu-id="f6756-114">Create a Python project</span></span>

1. <span data-ttu-id="f6756-115">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f6756-115">Pre-requisites</span></span>

     * <span data-ttu-id="f6756-116">[Sada pro vývoj pro](xref:microsoft.quantum.install#develop-with-python) všechna tato prostředí pro Python</span><span class="sxs-lookup"><span data-stu-id="f6756-116">The [Quantum Development Kit for Python](xref:microsoft.quantum.install#develop-with-python)</span></span>

1. <span data-ttu-id="f6756-117">Vytvořte složku pro váš projekt a přejděte do této složky.</span><span class="sxs-lookup"><span data-stu-id="f6756-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="f6756-118">Vytvořte soubor Q # s názvem `Operation.qs`a přidejte do něj svůj kód Q #.</span><span class="sxs-lookup"><span data-stu-id="f6756-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="f6756-119">Například:</span><span class="sxs-lookup"><span data-stu-id="f6756-119">For example:</span></span>

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

1. <span data-ttu-id="f6756-120">Vytvořte soubor hostitele Pythonu s názvem `host.py` pro volání operace Q #.</span><span class="sxs-lookup"><span data-stu-id="f6756-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="f6756-121">Například:</span><span class="sxs-lookup"><span data-stu-id="f6756-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="f6756-122">Spusťte program:</span><span class="sxs-lookup"><span data-stu-id="f6756-122">Run the program:</span></span>

    ```bash
    python host.py
    ```

1. <span data-ttu-id="f6756-123">Ověřte výstup.</span><span class="sxs-lookup"><span data-stu-id="f6756-123">Verify the output.</span></span> <span data-ttu-id="f6756-124">Program by měl mít výstup na následujících řádcích:</span><span class="sxs-lookup"><span data-stu-id="f6756-124">Your program should output the following lines:</span></span>

    ```bash
    Hello from quantum world!
    0
    ```

<span data-ttu-id="f6756-125">Nyní můžete pokračovat v vývoji programu pro práci s více.</span><span class="sxs-lookup"><span data-stu-id="f6756-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-jupyter-notebook-project"></a><span data-ttu-id="f6756-126">Vytvoření projektu Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="f6756-126">Create a Jupyter Notebook project</span></span>

1. <span data-ttu-id="f6756-127">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f6756-127">Pre-requisites</span></span>

    * <span data-ttu-id="f6756-128">[Vývojová sada pro všechna ta – Jupyter poznámkové bloky](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)</span><span class="sxs-lookup"><span data-stu-id="f6756-128">The [Quantum Development Kit for Jupyter notebooks](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)</span></span>

1. <span data-ttu-id="f6756-129">Spusťte následující příkaz, který spustí Poznámkový Server:</span><span class="sxs-lookup"><span data-stu-id="f6756-129">Run the following command to start the notebook server:</span></span>

    ```bash
    jupyter notebook
    ```

1. <span data-ttu-id="f6756-130">Přejděte na adresu URL zobrazenou na příkazovém řádku.</span><span class="sxs-lookup"><span data-stu-id="f6756-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="f6756-131">Například: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="f6756-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="f6756-132">V prohlížeči se zobrazí stránka Jupyter.</span><span class="sxs-lookup"><span data-stu-id="f6756-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="f6756-133">Na kartě **soubory** vyberte **Nový** > **Q #** a vytvořte Poznámkový blok Jupyter s jádrem Q #.</span><span class="sxs-lookup"><span data-stu-id="f6756-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter notebook with a Q# kernel.</span></span> <span data-ttu-id="f6756-134">Do první buňky poznámkového bloku přidejte následující kód:</span><span class="sxs-lookup"><span data-stu-id="f6756-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="f6756-135">Vyberte **buňku** > **Spustit buňky** pro spuštění poznámkového bloku.</span><span class="sxs-lookup"><span data-stu-id="f6756-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="f6756-136">`SayHello` se brzy objeví ve výstupu buňky:</span><span class="sxs-lookup"><span data-stu-id="f6756-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Buňka Jupyter Poznámkový blok s kódem Q #](~/media/install-guide-jupyter.png)

    <span data-ttu-id="f6756-138">Při spuštění v poznámkových blocích Jupyter se zkompiluje kód Q # a výstup poznámkového bloku vytvoří název operací, které najde.</span><span class="sxs-lookup"><span data-stu-id="f6756-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="f6756-139">V nové buňce Simulujte spuštění v počítačovém provozu operace, kterou jste právě vytvořili, pomocí `%simulate` Magic:</span><span class="sxs-lookup"><span data-stu-id="f6756-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![Buňka Jupyter poznámkového bloku s% simuluje Magic](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="f6756-141">Měla by se zobrazit zpráva vytištěná na obrazovce spolu s výsledkem operace, kterou jste vyvolali (v tomto případě je to prázdné).</span><span class="sxs-lookup"><span data-stu-id="f6756-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="f6756-142">Nyní můžete přidat další operace Q #, abyste mohli pokračovat ve vývoji vašeho vlastního navýšení.</span><span class="sxs-lookup"><span data-stu-id="f6756-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="f6756-143">Vytvoření C# projektu ve Windows pomocí sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f6756-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="f6756-144">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f6756-144">Pre-requisites</span></span>

    * <span data-ttu-id="f6756-145">[Sada pro vývoj pro všechna tato prostředí pro Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)</span><span class="sxs-lookup"><span data-stu-id="f6756-145">The [Quantum Development Kit for Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)</span></span>

1. <span data-ttu-id="f6756-146">Vytvoří novou aplikaci Q #.</span><span class="sxs-lookup"><span data-stu-id="f6756-146">Create a new Q# application</span></span>

    * <span data-ttu-id="f6756-147">Přejít na **soubor** -> **Nový** -> **projekt**</span><span class="sxs-lookup"><span data-stu-id="f6756-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="f6756-148">Do vyhledávacího pole zadejte `Q#`</span><span class="sxs-lookup"><span data-stu-id="f6756-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="f6756-149">Vybrat **aplikaci Q #**</span><span class="sxs-lookup"><span data-stu-id="f6756-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="f6756-150">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="f6756-150">Select **Next**</span></span>
    * <span data-ttu-id="f6756-151">Zvolit název a umístění vaší aplikace</span><span class="sxs-lookup"><span data-stu-id="f6756-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="f6756-152">Vyberte **Vytvořit**.</span><span class="sxs-lookup"><span data-stu-id="f6756-152">Select **Create**</span></span>

1. <span data-ttu-id="f6756-153">Kontrola projektu</span><span class="sxs-lookup"><span data-stu-id="f6756-153">Inspect the project</span></span>

    <span data-ttu-id="f6756-154">Měli byste vidět, že byly vytvořeny dva soubory: `Driver.cs`, což je C# hostitelská aplikace; a `Operation.qs`, což je program Q #, který definuje jednoduchou operaci pro tisk zprávy do konzoly.</span><span class="sxs-lookup"><span data-stu-id="f6756-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="f6756-155">Spuštění aplikace</span><span class="sxs-lookup"><span data-stu-id="f6756-155">Run the application</span></span>

    * <span data-ttu-id="f6756-156">Vyberte **ladění** -> **Spustit bez ladění**</span><span class="sxs-lookup"><span data-stu-id="f6756-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="f6756-157">Měl by se zobrazit text `Hello quantum world!` vytištěný v okně konzoly.</span><span class="sxs-lookup"><span data-stu-id="f6756-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="f6756-158">Nyní můžete pokračovat ve vývoji vašeho vlastního využití pomocí sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f6756-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="f6756-159">Pokud máte více projektů v rámci jednoho řešení sady Visual Studio, všechny projekty, které jsou obsaženy v řešení, musí být ve stejné složce jako řešení nebo v některé z jejích podsložek.</span><span class="sxs-lookup"><span data-stu-id="f6756-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="f6756-160">Vytvoření C# projektu pomocí vs Code</span><span class="sxs-lookup"><span data-stu-id="f6756-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="f6756-161">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f6756-161">Pre-requisites</span></span>

    * <span data-ttu-id="f6756-162">[Vývojová sada pro](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code) všechna tato prostředí pro vs Code</span><span class="sxs-lookup"><span data-stu-id="f6756-162">The [Quantum Development Kit for VS Code](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)</span></span>

1. <span data-ttu-id="f6756-163">Vytvořit nový projekt:</span><span class="sxs-lookup"><span data-stu-id="f6756-163">Create a new project:</span></span>

    * <span data-ttu-id="f6756-164">Přejít na **zobrazení** -> **paleta příkazů**</span><span class="sxs-lookup"><span data-stu-id="f6756-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="f6756-165">Vyberte **Q #: vytvořit nový projekt.**</span><span class="sxs-lookup"><span data-stu-id="f6756-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="f6756-166">Přejděte do umístění v systému souborů, kde chcete vytvořit aplikaci.</span><span class="sxs-lookup"><span data-stu-id="f6756-166">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="f6756-167">Po vytvoření projektu klikněte na tlačítko **Otevřít nový projekt...**</span><span class="sxs-lookup"><span data-stu-id="f6756-167">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="f6756-168">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="f6756-168">Run the application:</span></span>

    * <span data-ttu-id="f6756-169">Přejít na **ladění** -> **Spustit bez ladění**</span><span class="sxs-lookup"><span data-stu-id="f6756-169">Go to **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="f6756-170">V okně výstup byste měli vidět následující text `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="f6756-170">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="f6756-171">Nyní můžete pokračovat ve vývoji ve vaší práci pomocí Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="f6756-171">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="f6756-172">Rozšíření Visual Studio Code v současné době nepodporuje pracovní prostory s více kořenovými složkami.</span><span class="sxs-lookup"><span data-stu-id="f6756-172">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="f6756-173">Pokud máte více projektů v rámci jednoho VS Code pracovního prostoru, musí být všechny projekty obsaženy v rámci stejné kořenové složky.</span><span class="sxs-lookup"><span data-stu-id="f6756-173">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="f6756-174">Vytvoření C# projektu pomocí `dotnet` nástroje příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="f6756-174">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="f6756-175">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f6756-175">Pre-requisites</span></span>

    * <span data-ttu-id="f6756-176">[Sada pro vývoj pro](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool) všechna ta na příkazovém řádku</span><span class="sxs-lookup"><span data-stu-id="f6756-176">The [Quantum Development Kit for the Command Line](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)</span></span>

1. <span data-ttu-id="f6756-177">Vytvoření nové aplikace</span><span class="sxs-lookup"><span data-stu-id="f6756-177">Create a new application</span></span>

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="f6756-178">Přejít do nového adresáře aplikace</span><span class="sxs-lookup"><span data-stu-id="f6756-178">Navigate to the new application directory</span></span>

    ```bash
    cd <project name>
    ```

    <span data-ttu-id="f6756-179">Měli byste vidět, že byly vytvořeny dva soubory společně se soubory projektu aplikace: soubor Q # (`Operation.qs`) a soubor C# hostitele (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="f6756-179">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="f6756-180">Spuštění aplikace</span><span class="sxs-lookup"><span data-stu-id="f6756-180">Run the application</span></span>

    ```bash
    dotnet run
    ```

    <span data-ttu-id="f6756-181">Měl by se zobrazit následující výstup: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="f6756-181">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="f6756-182">Teď budete pokračovat ve vývoji ve vaší práci pomocí nástrojů příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="f6756-182">You now continue your quantum development, using command line tools.</span></span>

## <a name="whats-next"></a><span data-ttu-id="f6756-183">A co dál?</span><span class="sxs-lookup"><span data-stu-id="f6756-183">What's next?</span></span>

<span data-ttu-id="f6756-184">Teď, když jste vytvořili projekt v upřednostňovaném prostředí, můžete pokračovat ve vývoji vašeho vlastního navýšení.</span><span class="sxs-lookup"><span data-stu-id="f6756-184">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
