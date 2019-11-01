---
title: Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035277"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="7d392-102">Instalace sady Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="7d392-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="7d392-103">Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK), abyste mohli začít s kvantovým programováním.</span><span class="sxs-lookup"><span data-stu-id="7d392-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="7d392-104">Sada QDK obsahuje tyto komponenty:</span><span class="sxs-lookup"><span data-stu-id="7d392-104">The QDK consists of:</span></span>

- <span data-ttu-id="7d392-105">Programovací jazyk Q#</span><span class="sxs-lookup"><span data-stu-id="7d392-105">the Q# programming language</span></span>
- <span data-ttu-id="7d392-106">Sada knihoven s abstraktními komplexními funkcemi v jazyku Q#</span><span class="sxs-lookup"><span data-stu-id="7d392-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="7d392-107">Hostitelská aplikace (napsaná v Pythonu nebo v jazyku .NET), která spouští kvantové operace napsané v jazyku Q#</span><span class="sxs-lookup"><span data-stu-id="7d392-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="7d392-108">Nástroje pro usnadnění vývoje</span><span class="sxs-lookup"><span data-stu-id="7d392-108">tools to facilitate your development</span></span>

<span data-ttu-id="7d392-109">V závislosti na zvoleném vývojovém prostředí se provádějí rozdílné kroky instalace.</span><span class="sxs-lookup"><span data-stu-id="7d392-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="7d392-110">V následujících částech vyberte požadované prostředí.</span><span class="sxs-lookup"><span data-stu-id="7d392-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="7d392-111">Vývoj v Pythonu</span><span class="sxs-lookup"><span data-stu-id="7d392-111">Develop with Python</span></span>

1. <span data-ttu-id="7d392-112">Požadavky</span><span class="sxs-lookup"><span data-stu-id="7d392-112">Pre-requisites</span></span>

    - <span data-ttu-id="7d392-113">[Python](https://www.python.org/downloads/) 3.6 nebo novější</span><span class="sxs-lookup"><span data-stu-id="7d392-113">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="7d392-114">Správce balíčků Pythonu [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="7d392-114">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="7d392-115">.NET Core SDK 2.1 nebo novější</span><span class="sxs-lookup"><span data-stu-id="7d392-115">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="7d392-116">Nainstalujte balíček `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="7d392-116">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="7d392-117">Nainstalujte balíček `qsharp`.</span><span class="sxs-lookup"><span data-stu-id="7d392-117">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="7d392-118">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="7d392-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="7d392-119">Vytvořte minimální operaci v jazyku Q# tím, že vytvoříte soubor s názvem `Operation.qs` a do něj přidáte následující kód:</span><span class="sxs-lookup"><span data-stu-id="7d392-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - <span data-ttu-id="7d392-120">Vytvořte program v Pythonu s názvem `hello_world.py`, který bude volat operaci `SayHello()` jazyka Q#:</span><span class="sxs-lookup"><span data-stu-id="7d392-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="7d392-121">Spusťte program:</span><span class="sxs-lookup"><span data-stu-id="7d392-121">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="7d392-122">Ověřte výstup.</span><span class="sxs-lookup"><span data-stu-id="7d392-122">Verify the output.</span></span> <span data-ttu-id="7d392-123">Výstupem programu by měly být následující řádky:</span><span class="sxs-lookup"><span data-stu-id="7d392-123">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="7d392-124">Vývoj s využitím poznámkových bloků Jupyter</span><span class="sxs-lookup"><span data-stu-id="7d392-124">Develop with Jupyter notebooks</span></span>

1. <span data-ttu-id="7d392-125">Požadavky</span><span class="sxs-lookup"><span data-stu-id="7d392-125">Pre-requisites</span></span>

    - <span data-ttu-id="7d392-126">[Python](https://www.python.org/downloads/) 3.6 nebo novější</span><span class="sxs-lookup"><span data-stu-id="7d392-126">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="7d392-127">Poznámkový blok Jupyter</span><span class="sxs-lookup"><span data-stu-id="7d392-127">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="7d392-128">.NET Core SDK 2.1 nebo novější</span><span class="sxs-lookup"><span data-stu-id="7d392-128">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="7d392-129">Nainstalujte balíček `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="7d392-129">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="7d392-130">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="7d392-130">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="7d392-131">Spusťte následující příkaz, kterým se spustí server poznámkového bloku:</span><span class="sxs-lookup"><span data-stu-id="7d392-131">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="7d392-132">Přejděte na adresu URL zobrazenou na příkazovém řádku.</span><span class="sxs-lookup"><span data-stu-id="7d392-132">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="7d392-133">Příklad: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="7d392-133">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="7d392-134">Vytvořte poznámkový blok Jupyter s použitím jádra Q# a do první buňky poznámkového bloku přidejte následující kód:</span><span class="sxs-lookup"><span data-stu-id="7d392-134">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="7d392-135">Spusťte tuto buňku poznámkového bloku:</span><span class="sxs-lookup"><span data-stu-id="7d392-135">Run this cell of the notebook:</span></span>

        ![Buňka poznámkového bloku Jupyter](~/media/install-guide-jupyter.png)

        <span data-ttu-id="7d392-137">Ve výstupu buňky by se měl zobrazit text `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="7d392-137">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="7d392-138">Při spouštění v poznámkových blocích Jupyter se kompiluje kód v jazyku Q# a výstupem poznámkového bloku jsou názvy nalezených operací.</span><span class="sxs-lookup"><span data-stu-id="7d392-138">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="7d392-139">Vývoj v jazyku C# ve Windows s použitím sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7d392-139">Develop with C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="7d392-140">Požadavky</span><span class="sxs-lookup"><span data-stu-id="7d392-140">Pre-requisites</span></span>

    - <span data-ttu-id="7d392-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 s povolenými úlohami vývoje pro různé platformy pomocí rozhraní .NET Core</span><span class="sxs-lookup"><span data-stu-id="7d392-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="7d392-142">Nainstalujte rozšíření sady Visual Studio pro jazyk Q#.</span><span class="sxs-lookup"><span data-stu-id="7d392-142">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="7d392-143">Stáhněte si [rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="7d392-143">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="7d392-144">Přidejte rozšíření do sady Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7d392-144">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="7d392-145">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="7d392-145">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="7d392-146">Vytvořte novou aplikaci v jazyku Q#.</span><span class="sxs-lookup"><span data-stu-id="7d392-146">Create a new Q# application</span></span>

        - <span data-ttu-id="7d392-147">Přejděte do části **Soubor**  ->  **Nový**  ->  **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="7d392-147">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="7d392-148">Do vyhledávacího pole zadejte `Q#`.</span><span class="sxs-lookup"><span data-stu-id="7d392-148">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="7d392-149">Vyberte **Aplikace Q#** .</span><span class="sxs-lookup"><span data-stu-id="7d392-149">Select **Q# Application**</span></span>
        - <span data-ttu-id="7d392-150">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="7d392-150">Select **Next**</span></span>
        - <span data-ttu-id="7d392-151">Vyberte název a umístění aplikace.</span><span class="sxs-lookup"><span data-stu-id="7d392-151">Choose a name and location for your application</span></span>
        - <span data-ttu-id="7d392-152">Vyberte **Vytvořit**.</span><span class="sxs-lookup"><span data-stu-id="7d392-152">Select **Create**</span></span>

    - <span data-ttu-id="7d392-153">Prozkoumejte projekt.</span><span class="sxs-lookup"><span data-stu-id="7d392-153">Inspect the project</span></span>

        <span data-ttu-id="7d392-154">Měli byste zjistit, že byly vytvořeny dva soubory: `Driver.cs`, což je hostitelská aplikace C#, a `Operation.qs`, což je program v jazyku Q#, který definuje jednoduchou operaci zobrazení zprávy na konzole.</span><span class="sxs-lookup"><span data-stu-id="7d392-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="7d392-155">Spuštění aplikace</span><span class="sxs-lookup"><span data-stu-id="7d392-155">Run the application</span></span>

        - <span data-ttu-id="7d392-156">Vyberte **Ladit** -> **Spustit bez ladění**.</span><span class="sxs-lookup"><span data-stu-id="7d392-156">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="7d392-157">V okně konzoly by se měl zobrazit text `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="7d392-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="7d392-158">Pokud řešení sady Visual Studio obsahuje více projektů, musí se všechny projekty obsažené v řešení nacházet ve stejné složce jako řešení nebo v jedné z jejích podsložek.</span><span class="sxs-lookup"><span data-stu-id="7d392-158">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-vs-code"></a><span data-ttu-id="7d392-159">Vývoj v jazyku C# s využitím VS Code</span><span class="sxs-lookup"><span data-stu-id="7d392-159">Develop with C#, using VS Code</span></span>

1. <span data-ttu-id="7d392-160">Požadavky</span><span class="sxs-lookup"><span data-stu-id="7d392-160">Pre-requisites</span></span>

   - [<span data-ttu-id="7d392-161">VS Code</span><span class="sxs-lookup"><span data-stu-id="7d392-161">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="7d392-162">.NET Core SDK 2.1 nebo novější</span><span class="sxs-lookup"><span data-stu-id="7d392-162">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="7d392-163">Nainstalujte rozšíření VS Code pro kvantové programování.</span><span class="sxs-lookup"><span data-stu-id="7d392-163">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="7d392-164">Nainstalujte [rozšíření VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="7d392-164">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="7d392-165">Nainstalujte šablony kvantového projektu:</span><span class="sxs-lookup"><span data-stu-id="7d392-165">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="7d392-166">Přejděte do části **Zobrazit** -> **Paleta příkazů**.</span><span class="sxs-lookup"><span data-stu-id="7d392-166">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="7d392-167">Vyberte **Q#: Nainstalovat šablony projektu**.</span><span class="sxs-lookup"><span data-stu-id="7d392-167">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="7d392-168">Teď máte sadu Quantum Development Kit nainstalovanou a připravenou k používání ve vašich vlastních aplikacích a knihovnách.</span><span class="sxs-lookup"><span data-stu-id="7d392-168">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="7d392-169">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="7d392-169">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="7d392-170">Vytvořte nový projekt:</span><span class="sxs-lookup"><span data-stu-id="7d392-170">Create a new project:</span></span>

        - <span data-ttu-id="7d392-171">Přejděte do části **Zobrazit** -> **Paleta příkazů**.</span><span class="sxs-lookup"><span data-stu-id="7d392-171">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="7d392-172">Vyberte **Q#: Vytvořit nový projekt**.</span><span class="sxs-lookup"><span data-stu-id="7d392-172">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="7d392-173">Přejděte do umístění v systému souborů, ve kterém chcete aplikaci vytvořit.</span><span class="sxs-lookup"><span data-stu-id="7d392-173">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="7d392-174">Po vytvoření projektu klikněte na tlačítko **Otevřít nový projekt**.</span><span class="sxs-lookup"><span data-stu-id="7d392-174">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="7d392-175">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="7d392-175">Run the application:</span></span>

        - <span data-ttu-id="7d392-176">Přejděte do části **Ladit** -> **Spustit bez ladění**.</span><span class="sxs-lookup"><span data-stu-id="7d392-176">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="7d392-177">V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="7d392-177">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="7d392-178">Rozšíření Visual Studio Code aktuálně nepodporuje pracovní prostory s více kořenovými složkami.</span><span class="sxs-lookup"><span data-stu-id="7d392-178">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="7d392-179">Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.</span><span class="sxs-lookup"><span data-stu-id="7d392-179">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="7d392-180">Vývoj v jazyku C# s použitím nástroje pro příkazový řádek `dotnet`</span><span class="sxs-lookup"><span data-stu-id="7d392-180">Develop with C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="7d392-181">Požadavky</span><span class="sxs-lookup"><span data-stu-id="7d392-181">Pre-requisites</span></span>

    - [<span data-ttu-id="7d392-182">.NET Core SDK 2.1 nebo novější</span><span class="sxs-lookup"><span data-stu-id="7d392-182">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="7d392-183">Nainstalujte šablony kvantového projektu pro rozhraní .NET.</span><span class="sxs-lookup"><span data-stu-id="7d392-183">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="7d392-184">Teď máte sadu Quantum Development Kit nainstalovanou a připravenou k používání ve vašich vlastních aplikacích a knihovnách.</span><span class="sxs-lookup"><span data-stu-id="7d392-184">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="7d392-185">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="7d392-185">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="7d392-186">Vytvoření nové aplikace</span><span class="sxs-lookup"><span data-stu-id="7d392-186">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="7d392-187">Přejděte do adresáře nové aplikace.</span><span class="sxs-lookup"><span data-stu-id="7d392-187">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="7d392-188">Spolu se soubory projektu aplikace by se měly zobrazovat dva vytvořené soubory: soubor v jazyku Q# (`Operation.qs`) a soubor hostitele v jazyku C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="7d392-188">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="7d392-189">Spuštění aplikace</span><span class="sxs-lookup"><span data-stu-id="7d392-189">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="7d392-190">Měl by se zobrazit následující výstup: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="7d392-190">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="7d392-191">Co dále?</span><span class="sxs-lookup"><span data-stu-id="7d392-191">What's next?</span></span>

<span data-ttu-id="7d392-192">Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="7d392-192">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
