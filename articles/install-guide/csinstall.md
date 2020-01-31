---
title: 'Vývoj s Q # +C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 1fd829c684502092bb7491b0f46b5f690320c941
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831014"
---
# <a name="develop-with-q--c"></a><span data-ttu-id="f7c72-102">Vývoj s Q # +C#</span><span class="sxs-lookup"><span data-stu-id="f7c72-102">Develop with Q# + C#</span></span>

<span data-ttu-id="f7c72-103">Nainstalujte QDK pro vývoj C# hostitelských programů pro volání Q # Operations.</span><span class="sxs-lookup"><span data-stu-id="f7c72-103">Install the QDK to develop C# host programs to call Q# operations.</span></span>

<span data-ttu-id="f7c72-104">Q # je sestavený tak, aby se dobře hrál s jazyky C#.NET – konkrétně.</span><span class="sxs-lookup"><span data-stu-id="f7c72-104">Q# is built to play well with .NET languages--specifically C#.</span></span> <span data-ttu-id="f7c72-105">S tímto párováním můžete pracovat v různých vývojových prostředích:</span><span class="sxs-lookup"><span data-stu-id="f7c72-105">You can work with this pairing inside different development environments:</span></span>

- [<span data-ttu-id="f7c72-106">Q # + C# s použitím sady Visual Studio (Windows)</span><span class="sxs-lookup"><span data-stu-id="f7c72-106">Q# + C# using Visual Studio (Windows)</span></span>](#VS)
- [<span data-ttu-id="f7c72-107">Q # + C# použití Visual Studio Code (Windows, Linux a Mac)</span><span class="sxs-lookup"><span data-stu-id="f7c72-107">Q# + C# using Visual Studio Code (Windows, Linux and Mac)</span></span>](#VSC)
- [<span data-ttu-id="f7c72-108">Q # + C# použití nástroje příkazového řádku `dotnet`</span><span class="sxs-lookup"><span data-stu-id="f7c72-108">Q# + C# using the `dotnet` command-line tool</span></span>](#command)

## <span data-ttu-id="f7c72-109">Vývoj pomocí Q # + C# pomocí sady Visual Studio<a name="VS"></a></span><span class="sxs-lookup"><span data-stu-id="f7c72-109">Develop with Q# + C# using Visual Studio <a name="VS"></a></span></span>

<span data-ttu-id="f7c72-110">Visual Studio nabízí bohatá prostředí pro vývoj programů Q #.</span><span class="sxs-lookup"><span data-stu-id="f7c72-110">Visual Studio offers a rich environment for developing Q# programs.</span></span> <span data-ttu-id="f7c72-111">Rozšíření Visual Studio Q # obsahuje šablony pro soubory a projekty Q # a také zvýrazňování syntaxe, dokončování kódu a podporu technologie IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="f7c72-111">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting, code completion and IntelliSense support.</span></span>


1. <span data-ttu-id="f7c72-112">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f7c72-112">Pre-requisites</span></span>

    - <span data-ttu-id="f7c72-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 s povolenými úlohami vývoje pro různé platformy pomocí rozhraní .NET Core</span><span class="sxs-lookup"><span data-stu-id="f7c72-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="f7c72-114">Nainstalujte rozšíření sady Visual Studio pro jazyk Q#.</span><span class="sxs-lookup"><span data-stu-id="f7c72-114">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="f7c72-115">Stažení a instalace [rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="f7c72-115">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>

1. <span data-ttu-id="f7c72-116">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="f7c72-116">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="f7c72-117">Vytvořte novou aplikaci v jazyku Q#.</span><span class="sxs-lookup"><span data-stu-id="f7c72-117">Create a new Q# application</span></span>

        - <span data-ttu-id="f7c72-118">Přejděte do části **Soubor** -> **Nový** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="f7c72-118">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="f7c72-119">Do vyhledávacího pole zadejte `Q#`.</span><span class="sxs-lookup"><span data-stu-id="f7c72-119">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="f7c72-120">Vyberte **Aplikace Q#** .</span><span class="sxs-lookup"><span data-stu-id="f7c72-120">Select **Q# Application**</span></span>
        - <span data-ttu-id="f7c72-121">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="f7c72-121">Select **Next**</span></span>
        - <span data-ttu-id="f7c72-122">Vyberte název a umístění aplikace.</span><span class="sxs-lookup"><span data-stu-id="f7c72-122">Choose a name and location for your application</span></span>
        - <span data-ttu-id="f7c72-123">Vyberte **Vytvořit**.</span><span class="sxs-lookup"><span data-stu-id="f7c72-123">Select **Create**</span></span>

    - <span data-ttu-id="f7c72-124">Prozkoumejte projekt.</span><span class="sxs-lookup"><span data-stu-id="f7c72-124">Inspect the project</span></span>

        <span data-ttu-id="f7c72-125">Měli byste zjistit, že byly vytvořeny dva soubory: `Driver.cs`, což je hostitelská aplikace C#, a `Operation.qs`, což je program v jazyku Q#, který definuje jednoduchou operaci zobrazení zprávy na konzole.</span><span class="sxs-lookup"><span data-stu-id="f7c72-125">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="f7c72-126">Spuštění aplikace</span><span class="sxs-lookup"><span data-stu-id="f7c72-126">Run the application</span></span>

        - <span data-ttu-id="f7c72-127">Vyberte **Ladit** -> **Spustit bez ladění**.</span><span class="sxs-lookup"><span data-stu-id="f7c72-127">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="f7c72-128">V okně konzoly by se měl zobrazit text `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="f7c72-128">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="f7c72-129">Pokud řešení sady Visual Studio obsahuje více projektů, musí se všechny projekty obsažené v řešení nacházet ve stejné složce jako řešení nebo v jedné z jejích podsložek.</span><span class="sxs-lookup"><span data-stu-id="f7c72-129">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <span data-ttu-id="f7c72-130">Vývoj pomocí Q # + C# pomocí Visual Studio Code<a name="VSC"></a></span><span class="sxs-lookup"><span data-stu-id="f7c72-130">Develop with Q# + C# using Visual Studio Code <a name="VSC"></a></span></span>

<span data-ttu-id="f7c72-131">Visual Studio Code (VS Code) nabízí bohatý prostředí pro vývoj programů Q # v systémech Windows, Linux a Mac.</span><span class="sxs-lookup"><span data-stu-id="f7c72-131">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs on Windows, Linux and Mac.</span></span>  <span data-ttu-id="f7c72-132">Rozšíření Q # VS Code zahrnuje podporu zvýrazňování syntaxe Q #, dokončování kódu a fragmentů kódu Q #.</span><span class="sxs-lookup"><span data-stu-id="f7c72-132">The Q# VS Code extension includes support for Q# syntax highlighting, code completion, and Q# code snippets.</span></span>

1. <span data-ttu-id="f7c72-133">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f7c72-133">Pre-requisites</span></span>

   - [<span data-ttu-id="f7c72-134">VS Code</span><span class="sxs-lookup"><span data-stu-id="f7c72-134">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="f7c72-135">.NET Core SDK 3,1 nebo novější</span><span class="sxs-lookup"><span data-stu-id="f7c72-135">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="f7c72-136">Nainstalujte rozšíření VS Code pro kvantové programování.</span><span class="sxs-lookup"><span data-stu-id="f7c72-136">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="f7c72-137">Nainstalujte [rozšíření VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="f7c72-137">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="f7c72-138">Nainstalujte šablony kvantového projektu:</span><span class="sxs-lookup"><span data-stu-id="f7c72-138">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="f7c72-139">Přejděte do části **Zobrazit** -> **Paleta příkazů**.</span><span class="sxs-lookup"><span data-stu-id="f7c72-139">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="f7c72-140">Vyberte **Q #: Instalace šablon projektů**</span><span class="sxs-lookup"><span data-stu-id="f7c72-140">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="f7c72-141">Teď máte sadu Quantum Development Kit nainstalovanou a připravenou k používání ve vašich vlastních aplikacích a knihovnách.</span><span class="sxs-lookup"><span data-stu-id="f7c72-141">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="f7c72-142">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="f7c72-142">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="f7c72-143">Vytvořte nový projekt:</span><span class="sxs-lookup"><span data-stu-id="f7c72-143">Create a new project:</span></span>

        - <span data-ttu-id="f7c72-144">Přejděte do části **Zobrazit** -> **Paleta příkazů**.</span><span class="sxs-lookup"><span data-stu-id="f7c72-144">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="f7c72-145">Vyberte **Q #: vytvořit nový projekt.**</span><span class="sxs-lookup"><span data-stu-id="f7c72-145">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="f7c72-146">Vybrat **samostatnou konzolovou aplikaci**</span><span class="sxs-lookup"><span data-stu-id="f7c72-146">Select **Standalone console application**</span></span>
        - <span data-ttu-id="f7c72-147">Přejděte do umístění v systému souborů, ve kterém chcete aplikaci vytvořit.</span><span class="sxs-lookup"><span data-stu-id="f7c72-147">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="f7c72-148">Po vytvoření projektu klikněte na tlačítko **Otevřít nový projekt**.</span><span class="sxs-lookup"><span data-stu-id="f7c72-148">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="f7c72-149">Pokud ještě nemáte nainstalované C# rozšíření pro vs Code, zobrazí se automaticky otevírané okno.</span><span class="sxs-lookup"><span data-stu-id="f7c72-149">If you don't already have the C# extension for VS Code installed, a pop-up will appear.</span></span> <span data-ttu-id="f7c72-150">Nainstalujte rozšíření.</span><span class="sxs-lookup"><span data-stu-id="f7c72-150">Install the extension.</span></span> 

    - <span data-ttu-id="f7c72-151">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="f7c72-151">Run the application:</span></span>

        - <span data-ttu-id="f7c72-152">Přejít na **terminál** -> **nový terminál**</span><span class="sxs-lookup"><span data-stu-id="f7c72-152">Go to **Terminal** -> **New Terminal**</span></span>
        - <span data-ttu-id="f7c72-153">Zadejte `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="f7c72-153">Enter `dotnet run`</span></span>
        - <span data-ttu-id="f7c72-154">V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="f7c72-154">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="f7c72-155">Rozšíření Visual Studio Code aktuálně nepodporuje pracovní prostory s více kořenovými složkami.</span><span class="sxs-lookup"><span data-stu-id="f7c72-155">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="f7c72-156">Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.</span><span class="sxs-lookup"><span data-stu-id="f7c72-156">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <span data-ttu-id="f7c72-157">Vývoj pomocí Q # + C# pomocí nástroje příkazového řádku `dotnet`<a name="command"></a></span><span class="sxs-lookup"><span data-stu-id="f7c72-157">Develop with Q# + C# using the `dotnet` command-line tool <a name="command"></a></span></span>

<span data-ttu-id="f7c72-158">Samozřejmě můžete programy v Q# také sestavovat a spouštět z příkazového řádku. Stačí nainstalovat .NET Core SDK a šablony projektů QDK.</span><span class="sxs-lookup"><span data-stu-id="f7c72-158">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="f7c72-159">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f7c72-159">Pre-requisites</span></span>

    - [<span data-ttu-id="f7c72-160">.NET Core SDK 3,1 nebo novější</span><span class="sxs-lookup"><span data-stu-id="f7c72-160">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="f7c72-161">Nainstalujte šablony kvantového projektu pro rozhraní .NET.</span><span class="sxs-lookup"><span data-stu-id="f7c72-161">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="f7c72-162">Teď máte sadu Quantum Development Kit nainstalovanou a připravenou k používání ve vašich vlastních aplikacích a knihovnách.</span><span class="sxs-lookup"><span data-stu-id="f7c72-162">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="f7c72-163">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="f7c72-163">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="f7c72-164">Vytvoření nové aplikace</span><span class="sxs-lookup"><span data-stu-id="f7c72-164">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="f7c72-165">Přejděte do adresáře nové aplikace.</span><span class="sxs-lookup"><span data-stu-id="f7c72-165">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="f7c72-166">Spolu se soubory projektu aplikace by se měly zobrazovat dva vytvořené soubory: soubor v jazyku Q# (`Operation.qs`) a soubor hostitele v jazyku C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="f7c72-166">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="f7c72-167">Spuštění aplikace</span><span class="sxs-lookup"><span data-stu-id="f7c72-167">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="f7c72-168">Měl by se zobrazit následující výstup: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="f7c72-168">You should see the following output: `Hello quantum world!`</span></span>

    
## <a name="whats-next"></a><span data-ttu-id="f7c72-169">A co dál?</span><span class="sxs-lookup"><span data-stu-id="f7c72-169">What's next?</span></span>

<span data-ttu-id="f7c72-170">Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="f7c72-170">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
