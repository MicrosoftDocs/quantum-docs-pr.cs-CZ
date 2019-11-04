---
title: Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 090cf98612c6c549c733e54f9dcbf74442b30fbd
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442249"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="8fc44-102">Instalace sady Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="8fc44-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="8fc44-103">Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK), abyste mohli začít s kvantovým programováním.</span><span class="sxs-lookup"><span data-stu-id="8fc44-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="8fc44-104">Sada QDK obsahuje tyto komponenty:</span><span class="sxs-lookup"><span data-stu-id="8fc44-104">The QDK consists of:</span></span>

- <span data-ttu-id="8fc44-105">Programovací jazyk Q#</span><span class="sxs-lookup"><span data-stu-id="8fc44-105">the Q# programming language</span></span>
- <span data-ttu-id="8fc44-106">Sada knihoven s abstraktními komplexními funkcemi v jazyku Q#</span><span class="sxs-lookup"><span data-stu-id="8fc44-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="8fc44-107">Hostitelská aplikace (napsaná v Pythonu nebo v jazyku .NET), která spouští kvantové operace napsané v jazyku Q#</span><span class="sxs-lookup"><span data-stu-id="8fc44-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="8fc44-108">Nástroje pro usnadnění vývoje</span><span class="sxs-lookup"><span data-stu-id="8fc44-108">tools to facilitate your development</span></span>

<span data-ttu-id="8fc44-109">V závislosti na zvoleném vývojovém prostředí se provádějí rozdílné kroky instalace.</span><span class="sxs-lookup"><span data-stu-id="8fc44-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="8fc44-110">V následujících částech vyberte požadované prostředí.</span><span class="sxs-lookup"><span data-stu-id="8fc44-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="8fc44-111">Vývoj v Pythonu</span><span class="sxs-lookup"><span data-stu-id="8fc44-111">Develop with Python</span></span>

<span data-ttu-id="8fc44-112">Balíček qsharp pro Python usnadňuje simulaci operací a funkcí jazyka Q# v rámci Pythonu.</span><span class="sxs-lookup"><span data-stu-id="8fc44-112">The qsharp package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="8fc44-113">IQ# (anglicky se vyslovuje i-q-sharp) je rozšíření primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a simulaci operací v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="8fc44-113">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python that provides the core functionality for compiling and simulating Q# operations.</span></span>

1. <span data-ttu-id="8fc44-114">Požadavky</span><span class="sxs-lookup"><span data-stu-id="8fc44-114">Pre-requisites</span></span>

    - <span data-ttu-id="8fc44-115">[Python](https://www.python.org/downloads/) 3.6 nebo novější</span><span class="sxs-lookup"><span data-stu-id="8fc44-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="8fc44-116">Správce balíčků Pythonu [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="8fc44-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="8fc44-117">.NET Core SDK 3.0 nebo novější</span><span class="sxs-lookup"><span data-stu-id="8fc44-117">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="8fc44-118">Nainstalujte balíček `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="8fc44-118">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="8fc44-119">Nainstalujte balíček `qsharp`.</span><span class="sxs-lookup"><span data-stu-id="8fc44-119">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="8fc44-120">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="8fc44-120">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="8fc44-121">Vytvořte minimální operaci v jazyku Q# tím, že vytvoříte soubor s názvem `Operation.qs` a do něj přidáte následující kód:</span><span class="sxs-lookup"><span data-stu-id="8fc44-121">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

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

    - <span data-ttu-id="8fc44-122">Vytvořte program v Pythonu s názvem `hello_world.py`, který bude volat operaci `SayHello()` jazyka Q#:</span><span class="sxs-lookup"><span data-stu-id="8fc44-122">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="8fc44-123">Spusťte program:</span><span class="sxs-lookup"><span data-stu-id="8fc44-123">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="8fc44-124">Ověřte výstup.</span><span class="sxs-lookup"><span data-stu-id="8fc44-124">Verify the output.</span></span> <span data-ttu-id="8fc44-125">Výstupem programu by měly být následující řádky:</span><span class="sxs-lookup"><span data-stu-id="8fc44-125">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="8fc44-126">Vývoj s využitím poznámkových bloků Jupyter</span><span class="sxs-lookup"><span data-stu-id="8fc44-126">Develop with Jupyter notebooks</span></span>

<span data-ttu-id="8fc44-127">Poznámkové bloky Jupyter, které jsou oblíbené v akademickém prostředí, vědeckých laboratořích a také v rámci programování založeného na online spolupráci, nabízejí kromě pokynů, poznámek a dalšího obsahu také možnost místního spouštění kódu, nově včetně kódu v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="8fc44-127">A favorite of academic settings, scientific labs, and online-based collaborative programming, Jupyter Notebooks offer in-place code execution—now including Q# code—along with instructions, notes, and other content.</span></span>  <span data-ttu-id="8fc44-128">Podívejte se, co všechno k vytváření vlastních poznámkových bloků v Q# potřebujete.</span><span class="sxs-lookup"><span data-stu-id="8fc44-128">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="8fc44-129">IQ# (anglicky se vyslovuje i-q-sharp) je rozšíření sady .NET Core SDK primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a simulaci operací v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="8fc44-129">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>


1. <span data-ttu-id="8fc44-130">Požadavky</span><span class="sxs-lookup"><span data-stu-id="8fc44-130">Pre-requisites</span></span>

    - <span data-ttu-id="8fc44-131">[Python](https://www.python.org/downloads/) 3.6 nebo novější</span><span class="sxs-lookup"><span data-stu-id="8fc44-131">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="8fc44-132">Poznámkový blok Jupyter</span><span class="sxs-lookup"><span data-stu-id="8fc44-132">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="8fc44-133">.NET Core SDK 3.0 nebo novější</span><span class="sxs-lookup"><span data-stu-id="8fc44-133">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="8fc44-134">Nainstalujte balíček `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="8fc44-134">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="8fc44-135">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="8fc44-135">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="8fc44-136">Spusťte následující příkaz, kterým se spustí server poznámkového bloku:</span><span class="sxs-lookup"><span data-stu-id="8fc44-136">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="8fc44-137">Přejděte na adresu URL zobrazenou na příkazovém řádku.</span><span class="sxs-lookup"><span data-stu-id="8fc44-137">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="8fc44-138">Příklad: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="8fc44-138">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="8fc44-139">Vytvořte poznámkový blok Jupyter s použitím jádra Q# a do první buňky poznámkového bloku přidejte následující kód:</span><span class="sxs-lookup"><span data-stu-id="8fc44-139">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="8fc44-140">Spusťte tuto buňku poznámkového bloku:</span><span class="sxs-lookup"><span data-stu-id="8fc44-140">Run this cell of the notebook:</span></span>

        ![Buňka poznámkového bloku Jupyter s využitím kódu Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="8fc44-142">Ve výstupu buňky by se měl zobrazit text `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="8fc44-142">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="8fc44-143">Při spouštění v poznámkových blocích Jupyter se kompiluje kód v jazyku Q# a výstupem poznámkového bloku jsou názvy nalezených operací.</span><span class="sxs-lookup"><span data-stu-id="8fc44-143">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="8fc44-144">V nové buňce simulujte spuštění právě vytvořené operace v kvantovém počítači, a to pomocí příkazu magic `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="8fc44-144">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

        ![Buňka poznámkového bloku Jupyter s využitím příkazu magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="8fc44-146">Měla by se zobrazit zpráva na obrazovce spolu s výsledkem operace, kterou jste vyvolali (v tomto případě prázdným).</span><span class="sxs-lookup"><span data-stu-id="8fc44-146">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>


## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="8fc44-147">Vývoj v jazyku C# ve Windows s použitím sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8fc44-147">Develop with C# on Windows, using Visual Studio</span></span>

<span data-ttu-id="8fc44-148">Visual Studio nabízí bohaté prostředí pro vývoj programů v Q# se skvělými funkcemi, jako je dokončování kódu a zvýrazňování syntaxe, které vývojářům pomáhají při vytváření aplikací.</span><span class="sxs-lookup"><span data-stu-id="8fc44-148">Visual Studio offers a rich environment for developing Q# programs, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="8fc44-149">Rozšíření Q# Visual Studio obsahuje šablony pro projekty a soubory v Q# a také zvýrazňování syntaxe a podporu technologie IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="8fc44-149">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting and IntelliSense support.</span></span>


1. <span data-ttu-id="8fc44-150">Požadavky</span><span class="sxs-lookup"><span data-stu-id="8fc44-150">Pre-requisites</span></span>

    - <span data-ttu-id="8fc44-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 s povolenými úlohami vývoje pro různé platformy pomocí rozhraní .NET Core</span><span class="sxs-lookup"><span data-stu-id="8fc44-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="8fc44-152">Nainstalujte rozšíření sady Visual Studio pro jazyk Q#.</span><span class="sxs-lookup"><span data-stu-id="8fc44-152">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="8fc44-153">Stáhněte si [rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="8fc44-153">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="8fc44-154">Přidejte rozšíření do sady Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8fc44-154">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="8fc44-155">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="8fc44-155">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="8fc44-156">Vytvořte novou aplikaci v jazyku Q#.</span><span class="sxs-lookup"><span data-stu-id="8fc44-156">Create a new Q# application</span></span>

        - <span data-ttu-id="8fc44-157">Přejděte do části **Soubor**  ->  **Nový**  ->  **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="8fc44-157">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="8fc44-158">Do vyhledávacího pole zadejte `Q#`.</span><span class="sxs-lookup"><span data-stu-id="8fc44-158">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="8fc44-159">Vyberte **Aplikace Q#** .</span><span class="sxs-lookup"><span data-stu-id="8fc44-159">Select **Q# Application**</span></span>
        - <span data-ttu-id="8fc44-160">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="8fc44-160">Select **Next**</span></span>
        - <span data-ttu-id="8fc44-161">Vyberte název a umístění aplikace.</span><span class="sxs-lookup"><span data-stu-id="8fc44-161">Choose a name and location for your application</span></span>
        - <span data-ttu-id="8fc44-162">Vyberte **Vytvořit**.</span><span class="sxs-lookup"><span data-stu-id="8fc44-162">Select **Create**</span></span>

    - <span data-ttu-id="8fc44-163">Prozkoumejte projekt.</span><span class="sxs-lookup"><span data-stu-id="8fc44-163">Inspect the project</span></span>

        <span data-ttu-id="8fc44-164">Měli byste zjistit, že byly vytvořeny dva soubory: `Driver.cs`, což je hostitelská aplikace C#, a `Operation.qs`, což je program v jazyku Q#, který definuje jednoduchou operaci zobrazení zprávy na konzole.</span><span class="sxs-lookup"><span data-stu-id="8fc44-164">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="8fc44-165">Spuštění aplikace</span><span class="sxs-lookup"><span data-stu-id="8fc44-165">Run the application</span></span>

        - <span data-ttu-id="8fc44-166">Vyberte **Ladit** -> **Spustit bez ladění**.</span><span class="sxs-lookup"><span data-stu-id="8fc44-166">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="8fc44-167">V okně konzoly by se měl zobrazit text `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="8fc44-167">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="8fc44-168">Pokud řešení sady Visual Studio obsahuje více projektů, musí se všechny projekty obsažené v řešení nacházet ve stejné složce jako řešení nebo v jedné z jejích podsložek.</span><span class="sxs-lookup"><span data-stu-id="8fc44-168">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-visual-studio-code"></a><span data-ttu-id="8fc44-169">Vývoj s využitím C# v editoru Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8fc44-169">Develop with C#, using Visual Studio Code</span></span>

<span data-ttu-id="8fc44-170">Visual Studio Code (VS Code) nabízí bohaté prostředí pro vývoj programů v Q# napříč různými výpočetními prostředími, včetně systémů Windows, Linux a Mac, a poskytuje skvělé funkce, jako je dokončování kódu a zvýrazňování syntaxe, které vývojářům pomáhají při vytváření aplikací.</span><span class="sxs-lookup"><span data-stu-id="8fc44-170">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs across many multiple computer environments, including Windows, Linux and Mac, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="8fc44-171">Rozšíření Q# VS Code obsahuje zvýrazňování syntaxe a fragmenty kódu v Q#.</span><span class="sxs-lookup"><span data-stu-id="8fc44-171">The Q# VS Code extension contains syntax highlighting, and Q# code snippets.</span></span>

<span data-ttu-id="8fc44-172">Visual Studio Code (VS Code) nabízí bohaté prostředí pro vývoj programů v Q# napříč různými výpočetními prostředími, včetně systémů Windows, Linux a Mac, a poskytuje skvělé funkce, jako je dokončování kódu a zvýrazňování syntaxe, které vývojářům pomáhají při vytváření aplikací.</span><span class="sxs-lookup"><span data-stu-id="8fc44-172">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs across many multiple computer environments, including Windows, Linux and Mac, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="8fc44-173">Rozšíření Q# VS Code obsahuje zvýrazňování syntaxe a fragmenty kódu v Q#.</span><span class="sxs-lookup"><span data-stu-id="8fc44-173">The Q# VS Code extension contains syntax highlighting, and Q# code snippets.</span></span>

1. <span data-ttu-id="8fc44-174">Požadavky</span><span class="sxs-lookup"><span data-stu-id="8fc44-174">Pre-requisites</span></span>

   - [<span data-ttu-id="8fc44-175">VS Code</span><span class="sxs-lookup"><span data-stu-id="8fc44-175">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="8fc44-176">.NET Core SDK 3.0 nebo novější</span><span class="sxs-lookup"><span data-stu-id="8fc44-176">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="8fc44-177">Nainstalujte rozšíření VS Code pro kvantové programování.</span><span class="sxs-lookup"><span data-stu-id="8fc44-177">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="8fc44-178">Nainstalujte [rozšíření VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="8fc44-178">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="8fc44-179">Nainstalujte šablony kvantového projektu:</span><span class="sxs-lookup"><span data-stu-id="8fc44-179">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="8fc44-180">Přejděte do části **Zobrazit** -> **Paleta příkazů**.</span><span class="sxs-lookup"><span data-stu-id="8fc44-180">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="8fc44-181">Vyberte **Q#: Nainstalovat šablony projektu**.</span><span class="sxs-lookup"><span data-stu-id="8fc44-181">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="8fc44-182">Teď máte sadu Quantum Development Kit nainstalovanou a připravenou k používání ve vašich vlastních aplikacích a knihovnách.</span><span class="sxs-lookup"><span data-stu-id="8fc44-182">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="8fc44-183">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="8fc44-183">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="8fc44-184">Vytvořte nový projekt:</span><span class="sxs-lookup"><span data-stu-id="8fc44-184">Create a new project:</span></span>

        - <span data-ttu-id="8fc44-185">Přejděte do části **Zobrazit** -> **Paleta příkazů**.</span><span class="sxs-lookup"><span data-stu-id="8fc44-185">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="8fc44-186">Vyberte **Q#: Vytvořit nový projekt**.</span><span class="sxs-lookup"><span data-stu-id="8fc44-186">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="8fc44-187">Přejděte do umístění v systému souborů, ve kterém chcete aplikaci vytvořit.</span><span class="sxs-lookup"><span data-stu-id="8fc44-187">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="8fc44-188">Po vytvoření projektu klikněte na tlačítko **Otevřít nový projekt**.</span><span class="sxs-lookup"><span data-stu-id="8fc44-188">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="8fc44-189">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="8fc44-189">Run the application:</span></span>

        - <span data-ttu-id="8fc44-190">Přejděte do části **Ladit** -> **Spustit bez ladění**.</span><span class="sxs-lookup"><span data-stu-id="8fc44-190">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="8fc44-191">V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="8fc44-191">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="8fc44-192">Rozšíření Visual Studio Code aktuálně nepodporuje pracovní prostory s více kořenovými složkami.</span><span class="sxs-lookup"><span data-stu-id="8fc44-192">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="8fc44-193">Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.</span><span class="sxs-lookup"><span data-stu-id="8fc44-193">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="8fc44-194">Vývoj v jazyku C# s použitím nástroje pro příkazový řádek `dotnet`</span><span class="sxs-lookup"><span data-stu-id="8fc44-194">Develop with C#, using the `dotnet` command-line tool</span></span>

<span data-ttu-id="8fc44-195">Samozřejmě můžete programy v Q# také sestavovat a spouštět z příkazového řádku. Stačí nainstalovat .NET Core SDK a šablony projektů QDK.</span><span class="sxs-lookup"><span data-stu-id="8fc44-195">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="8fc44-196">Požadavky</span><span class="sxs-lookup"><span data-stu-id="8fc44-196">Pre-requisites</span></span>

    - [<span data-ttu-id="8fc44-197">.NET Core SDK 3.0 nebo novější</span><span class="sxs-lookup"><span data-stu-id="8fc44-197">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="8fc44-198">Nainstalujte šablony kvantového projektu pro rozhraní .NET.</span><span class="sxs-lookup"><span data-stu-id="8fc44-198">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="8fc44-199">Teď máte sadu Quantum Development Kit nainstalovanou a připravenou k používání ve vašich vlastních aplikacích a knihovnách.</span><span class="sxs-lookup"><span data-stu-id="8fc44-199">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="8fc44-200">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="8fc44-200">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="8fc44-201">Vytvoření nové aplikace</span><span class="sxs-lookup"><span data-stu-id="8fc44-201">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="8fc44-202">Přejděte do adresáře nové aplikace.</span><span class="sxs-lookup"><span data-stu-id="8fc44-202">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="8fc44-203">Spolu se soubory projektu aplikace by se měly zobrazovat dva vytvořené soubory: soubor v jazyku Q# (`Operation.qs`) a soubor hostitele v jazyku C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="8fc44-203">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="8fc44-204">Spuštění aplikace</span><span class="sxs-lookup"><span data-stu-id="8fc44-204">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="8fc44-205">Měl by se zobrazit následující výstup: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="8fc44-205">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="8fc44-206">Co dále?</span><span class="sxs-lookup"><span data-stu-id="8fc44-206">What's next?</span></span>

<span data-ttu-id="8fc44-207">Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="8fc44-207">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
