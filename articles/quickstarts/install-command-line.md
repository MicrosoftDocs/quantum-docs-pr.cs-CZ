---
title: Vývoj s aplikacemi v Q# v integrovaném vývojovém prostředí
description: Naučte se vytvářet aplikace Q#, které se spouští z příkazového řádku.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3e4f1e97477ecb0547b1586b1c7603c8a9954584
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844321"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a><span data-ttu-id="ddd5f-103">Vývoj s aplikacemi v Q# v integrovaném vývojovém prostředí</span><span class="sxs-lookup"><span data-stu-id="ddd5f-103">Develop with Q# applications in an IDE</span></span>

<span data-ttu-id="ddd5f-104">Programy v Q# se dají spouštět samostatně, bez ovladače v hostitelském jazyce jako C#, F# nebo Python.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-104">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span> <span data-ttu-id="ddd5f-105">K vývoji aplikací v Q# můžete použít Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces nebo libovolný jiný editor/IDE a spouštět aplikace z konzoly .NET.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-105">You can develop Q# applications in Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces, or with any editor/IDE and run applications from the .NET console.</span></span> 

## <a name="prerequisites-for-all-environments"></a><span data-ttu-id="ddd5f-106">Požadavky pro všechna prostředí</span><span class="sxs-lookup"><span data-stu-id="ddd5f-106">Prerequisites for all environments</span></span>

- [<span data-ttu-id="ddd5f-107">.NET Core SDK 3.1 nebo novější</span><span class="sxs-lookup"><span data-stu-id="ddd5f-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="ddd5f-108">Instalace</span><span class="sxs-lookup"><span data-stu-id="ddd5f-108">Installation</span></span>

<span data-ttu-id="ddd5f-109">I když můžete aplikaci v Q# sestavit v jakémkoli integrovaném vývojovém prostředí, doporučujeme použít Visual Studio Code (VS Code) nebo Visual Studio IDE nebo vyvíjet aplikace v Q# místně.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="ddd5f-110">Pro vývoj v cloudu prostřednictvím webového prohlížeče doporučujeme Visual Studio Codespaces.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="ddd5f-111">Vývoj v těchto prostředích využívá bohaté funkce rozšíření QDK, mezi které patří upozornění, zvýrazňování syntaxe, šablony projektů a další.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-111">Developing in these environments leverages the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

### <a name="to-configure-for-vs-code"></a><span data-ttu-id="ddd5f-112">Konfigurace pro VS Code:</span><span class="sxs-lookup"><span data-stu-id="ddd5f-112">To configure for VS Code:</span></span>

1. <span data-ttu-id="ddd5f-113">Stáhněte si a nainstalujte [VS Code](https://code.visualstudio.com/download) (Windows, Linux a Mac).</span><span class="sxs-lookup"><span data-stu-id="ddd5f-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="ddd5f-114">Nainstalujte [Microsoft QDK pro VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="ddd5f-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

### <a name="to-configure-for-visual-studio"></a><span data-ttu-id="ddd5f-115">Konfigurace pro Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="ddd5f-115">To configure for Visual Studio:</span></span>

1. <span data-ttu-id="ddd5f-116">Stáhněte si a nainstalujte [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 nebo novější s podporou multiplatformního vývoje .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="ddd5f-117">Stáhněte si a nainstalujte [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="ddd5f-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

### <a name="to-configure-for-another-environment"></a><span data-ttu-id="ddd5f-118">Konfigurace pro jiné prostředí:</span><span class="sxs-lookup"><span data-stu-id="ddd5f-118">To configure for another environment:</span></span> 

1. <span data-ttu-id="ddd5f-119">Na příkazovém řádku zadejte následující:</span><span class="sxs-lookup"><span data-stu-id="ddd5f-119">Enter the following at the command prompt</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a><span data-ttu-id="ddd5f-120">Konfigurace pro Visual Studio Codespaces:</span><span class="sxs-lookup"><span data-stu-id="ddd5f-120">To configure for Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="ddd5f-121">Vytvořte [účet Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="ddd5f-121">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="ddd5f-122">Vytvořte prostředí Codespaces.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-122">Create a Codespaces environment.</span></span> <span data-ttu-id="ddd5f-123">Postupujte podle [průvodce rychlým zprovozněním](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="ddd5f-123">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="ddd5f-124">Při vytváření Codespace doporučujeme do pole úložiště Git zadat `microsoft/Quantum` a načíst nastavení specifická pro QDK.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-124">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="ddd5f-125">Teď můžete nové prostředí spustit a začít vyvíjet v prohlížeči prostřednictvím [cloudového integrovaného vývojového prostředí VS Codespaces](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="ddd5f-125">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="ddd5f-126">Další možností je využít místní instalaci editoru VS Code a použít Codespaces jako [vzdálené prostředí](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="ddd5f-126">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>

## <a name="develop-with-no-locq"></a><span data-ttu-id="ddd5f-127">Vývoj s využitím Q#</span><span class="sxs-lookup"><span data-stu-id="ddd5f-127">Develop with Q#</span></span>

<span data-ttu-id="ddd5f-128">Postupujte podle pokynů na kartě odpovídající vašemu vývojovému prostředí.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-128">Follow the instructions on the tab corresponding to your development environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="ddd5f-129">VS Code</span><span class="sxs-lookup"><span data-stu-id="ddd5f-129">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="ddd5f-130">Vytvoření nového projektu:</span><span class="sxs-lookup"><span data-stu-id="ddd5f-130">To create a new project:</span></span>

1. <span data-ttu-id="ddd5f-131">Klikněte na **Zobrazení** -> **Paleta příkazů** a vyberte **Q#: Vytvořit nový projekt**.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-131">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="ddd5f-132">Klikněte na **Samostatná konzolová aplikace**.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-132">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="ddd5f-133">Přejděte do umístění, kam chcete projekt uložit.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-133">Navigate to the location to save the project.</span></span> <span data-ttu-id="ddd5f-134">Zadejte název projektu a klikněte na **Vytvořit projekt**.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-134">Enter the project name and click **Create Project**.</span></span>
4. <span data-ttu-id="ddd5f-135">Po úspěšném vytvoření projektu klikněte na **Otevřít nový projekt...** v pravém dolním rohu.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-135">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="ddd5f-136">Prozkoumejte projekt.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-136">Inspect the project.</span></span> <span data-ttu-id="ddd5f-137">Měl by se zobrazit zdrojový soubor s názvem `Program.qs`, což je program v Q#, který definuje jednoduchou operaci pro tisk zprávy na konzolu.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-137">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="ddd5f-138">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="ddd5f-138">To run the application:</span></span>

1. <span data-ttu-id="ddd5f-139">Klikněte na **Terminál** -> **Nový Terminál**.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-139">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="ddd5f-140">Na příkazovém řádku terminálu zadejte `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-140">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="ddd5f-141">V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="ddd5f-141">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="ddd5f-142">Rozšíření Q# pro VS Code aktuálně nepodporuje pracovní prostory s více kořenovými složkami.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-142">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="ddd5f-143">Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-143">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="ddd5f-144">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ddd5f-144">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="ddd5f-145">Ověřte instalaci sady Visual Studio vytvořením aplikace Q# `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-145">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="ddd5f-146">Vytvoření nové aplikace v Q#:</span><span class="sxs-lookup"><span data-stu-id="ddd5f-146">To create a new Q# application:</span></span>

1. <span data-ttu-id="ddd5f-147">Otevřete Visual Studio a klikněte na **Soubor** -> **Nový** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-147">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="ddd5f-148">Do vyhledávacího pole zadejte `Q#`, vyberte **Aplikace vQ#** a klikněte na **Další**.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-148">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="ddd5f-149">Zadejte název a umístění vaší aplikace a klikněte na **Vytvořit**.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-149">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="ddd5f-150">Prozkoumejte projekt.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-150">Inspect the project.</span></span> <span data-ttu-id="ddd5f-151">Měl by se zobrazit zdrojový soubor s názvem `Program.qs`, což je program v Q#, který definuje jednoduchou operaci pro tisk zprávy na konzolu.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-151">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="ddd5f-152">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="ddd5f-152">To run the application:</span></span>

1. <span data-ttu-id="ddd5f-153">Vyberte **Ladit** -> **Spustit bez ladění**.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-153">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="ddd5f-154">V okně konzoly by se měl zobrazit text `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-154">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="ddd5f-155">Pokud máte v jednom řešení sady Visual Studio více projektů, všechny projekty obsažené v řešení se musí nacházet ve stejné složce jako řešení nebo v jedné z jejích podsložek.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-155">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="ddd5f-156">Další editory s příkazovým řádkem</span><span class="sxs-lookup"><span data-stu-id="ddd5f-156">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="ddd5f-157">Ověřte instalaci vytvořením aplikace Q# `Hello World`</span><span class="sxs-lookup"><span data-stu-id="ddd5f-157">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="ddd5f-158">Vytvoření nové aplikace:</span><span class="sxs-lookup"><span data-stu-id="ddd5f-158">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="ddd5f-159">Přejděte do adresáře aplikace:</span><span class="sxs-lookup"><span data-stu-id="ddd5f-159">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="ddd5f-160">Tento adresář by měl nyní obsahovat soubor s názvem `Program.qs`, což je program v Q#, který definuje jednoduchou operaci pro tisk zprávy na konzolu.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-160">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="ddd5f-161">Tuto šablonu můžete upravit pomocí textového editoru a přepsat ji vlastními kvantovými aplikacemi.</span><span class="sxs-lookup"><span data-stu-id="ddd5f-161">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="ddd5f-162">Spusťte program:</span><span class="sxs-lookup"><span data-stu-id="ddd5f-162">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="ddd5f-163">Měl by se vypsat následující text: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="ddd5f-163">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="ddd5f-164">Další kroky</span><span class="sxs-lookup"><span data-stu-id="ddd5f-164">Next steps</span></span>

<span data-ttu-id="ddd5f-165">Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="ddd5f-165">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
