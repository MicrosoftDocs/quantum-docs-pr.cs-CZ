---
title: Vývoj aplikací příkazového řádku v Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 3d70838289e72afdd0a48bbdff0bec407428d125
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871429"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="c803f-102">Vývoj aplikací příkazového řádku v Q#</span><span class="sxs-lookup"><span data-stu-id="c803f-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="c803f-103">Programy Q# se dají spouštět samostatně, bez ovladače v hostitelském jazyce jako C#, F# nebo Python.</span><span class="sxs-lookup"><span data-stu-id="c803f-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c803f-104">Požadavky</span><span class="sxs-lookup"><span data-stu-id="c803f-104">Prerequisites</span></span>

- [<span data-ttu-id="c803f-105">.NET Core SDK 3.1 nebo novější</span><span class="sxs-lookup"><span data-stu-id="c803f-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="c803f-106">Instalace</span><span class="sxs-lookup"><span data-stu-id="c803f-106">Installation</span></span>

<span data-ttu-id="c803f-107">I když můžete aplikaci příkazového řádku Q# sestavit v jakémkoli integrovaném vývojovém prostředí, doporučujeme použít Visual Studio Code (VS Code) nebo Visual Studio IDE nebo vyvíjet aplikace v Q# místně.</span><span class="sxs-lookup"><span data-stu-id="c803f-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="c803f-108">Pro vývoj v cloudu prostřednictvím webového prohlížeče doporučujeme Visual Studio Codespaces.</span><span class="sxs-lookup"><span data-stu-id="c803f-108">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="c803f-109">Vývoj v těchto prostředích poskytuje bohaté funkce rozšíření QDK, mezi které patří upozornění, zvýrazňování syntaxe, šablony projektů a další.</span><span class="sxs-lookup"><span data-stu-id="c803f-109">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="c803f-110">Konfigurace VS Code:</span><span class="sxs-lookup"><span data-stu-id="c803f-110">To configure VS Code:</span></span>

1. <span data-ttu-id="c803f-111">Stáhněte si a nainstalujte [VS Code](https://code.visualstudio.com/download) (Windows, Linux a Mac).</span><span class="sxs-lookup"><span data-stu-id="c803f-111">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="c803f-112">Nainstalujte [Microsoft QDK pro VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="c803f-112">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="c803f-113">Konfigurace sady Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="c803f-113">To configure Visual Studio:</span></span>

1. <span data-ttu-id="c803f-114">Stáhněte si a nainstalujte [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 nebo novější s podporou multiplatformního vývoje .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c803f-114">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="c803f-115">Stáhněte si a nainstalujte [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="c803f-115">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="c803f-116">Konfigurace Visual Studio Codespaces:</span><span class="sxs-lookup"><span data-stu-id="c803f-116">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="c803f-117">Vytvořte [účet Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="c803f-117">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="c803f-118">Vytvořte prostředí Codespaces.</span><span class="sxs-lookup"><span data-stu-id="c803f-118">Create a Codespaces environment.</span></span> <span data-ttu-id="c803f-119">Postupujte podle [průvodce rychlým zprovozněním](https://docs.microsoft.com/visualstudio/online/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="c803f-119">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/online/quickstarts/browser).</span></span> <span data-ttu-id="c803f-120">Při vytváření Codespace doporučujeme do pole úložiště Git zadat `microsoft/Quantum` a načíst nastavení specifická pro QDK.</span><span class="sxs-lookup"><span data-stu-id="c803f-120">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="c803f-121">Teď můžete nové prostředí spustit a začít vyvíjet v prohlížeči prostřednictvím [cloudového integrovaného vývojového prostředí VS Codespaces](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="c803f-121">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="c803f-122">Další možností je využít místní instalaci editoru VS Code a použít Codespaces jako [vzdálené prostředí](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="c803f-122">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="c803f-123">Pokud chcete nainstalovat QDK pro jiné prostředí, zadejte do příkazového řádku:</span><span class="sxs-lookup"><span data-stu-id="c803f-123">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a><span data-ttu-id="c803f-124">Vývoj s využitím Q#</span><span class="sxs-lookup"><span data-stu-id="c803f-124">Develop with Q#</span></span>

<span data-ttu-id="c803f-125">Postupujte podle pokynů na kartě odpovídající vašemu prostředí.</span><span class="sxs-lookup"><span data-stu-id="c803f-125">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="c803f-126">VS Code</span><span class="sxs-lookup"><span data-stu-id="c803f-126">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c803f-127">Vytvoření nového projektu:</span><span class="sxs-lookup"><span data-stu-id="c803f-127">To create a new project:</span></span>

1. <span data-ttu-id="c803f-128">Klikněte na **Zobrazení** -> **Paleta příkazů** a vyberte **Q#: Vytvořit nový projekt**.</span><span class="sxs-lookup"><span data-stu-id="c803f-128">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="c803f-129">Klikněte na **Samostatná konzolová aplikace**.</span><span class="sxs-lookup"><span data-stu-id="c803f-129">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="c803f-130">Přejděte do umístění, kam chcete projekt uložit, a klikněte na **Vytvořit projekt**.</span><span class="sxs-lookup"><span data-stu-id="c803f-130">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="c803f-131">Po úspěšném vytvoření projektu klikněte na **Otevřít nový projekt...** v pravém dolním rohu.</span><span class="sxs-lookup"><span data-stu-id="c803f-131">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="c803f-132">Prozkoumejte projekt.</span><span class="sxs-lookup"><span data-stu-id="c803f-132">Inspect the project.</span></span> <span data-ttu-id="c803f-133">Měl by se zobrazit zdrojový soubor s názvem `Program.qs`, což je program Q#, který definuje jednoduchou operaci pro tisk zprávy na konzolu.</span><span class="sxs-lookup"><span data-stu-id="c803f-133">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="c803f-134">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="c803f-134">To run the application:</span></span>
1. <span data-ttu-id="c803f-135">Klikněte na **Terminál** -> **Nový Terminál**.</span><span class="sxs-lookup"><span data-stu-id="c803f-135">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="c803f-136">Na příkazovém řádku terminálu zadejte `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="c803f-136">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="c803f-137">V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="c803f-137">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="c803f-138">Rozšíření Q# pro VS Code aktuálně nepodporuje pracovní prostory s více kořenovými složkami.</span><span class="sxs-lookup"><span data-stu-id="c803f-138">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="c803f-139">Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.</span><span class="sxs-lookup"><span data-stu-id="c803f-139">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="c803f-140">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c803f-140">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="c803f-141">Ověřte instalaci sady Visual Studio vytvořením aplikace `Hello World` v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="c803f-141">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="c803f-142">Vytvoření nové aplikace v jazyce Q#:</span><span class="sxs-lookup"><span data-stu-id="c803f-142">To create a new Q# application:</span></span>
1. <span data-ttu-id="c803f-143">Otevřete Visual Studio a klikněte na **Soubor** -> **Nový** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="c803f-143">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="c803f-144">Do vyhledávacího pole zadejte `Q#`, vyberte **Aplikace Q#** a klikněte na **Další**.</span><span class="sxs-lookup"><span data-stu-id="c803f-144">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="c803f-145">Zadejte název a umístění vaší aplikace a klikněte na **Vytvořit**.</span><span class="sxs-lookup"><span data-stu-id="c803f-145">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="c803f-146">Prozkoumejte projekt.</span><span class="sxs-lookup"><span data-stu-id="c803f-146">Inspect the project.</span></span> <span data-ttu-id="c803f-147">Měl by se zobrazit zdrojový soubor s názvem `Program.qs`, což je program Q#, který definuje jednoduchou operaci pro tisk zprávy na konzolu.</span><span class="sxs-lookup"><span data-stu-id="c803f-147">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="c803f-148">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="c803f-148">To run the application:</span></span>
1. <span data-ttu-id="c803f-149">Vyberte **Ladit** -> **Spustit bez ladění**.</span><span class="sxs-lookup"><span data-stu-id="c803f-149">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="c803f-150">V okně konzoly by se měl zobrazit text `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="c803f-150">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="c803f-151">Pokud máte v jednom řešení sady Visual Studio více projektů, všechny projekty obsažené v řešení se musí nacházet ve stejné složce jako řešení nebo v jedné z jejích podsložek.</span><span class="sxs-lookup"><span data-stu-id="c803f-151">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="c803f-152">Další editory s příkazovým řádkem</span><span class="sxs-lookup"><span data-stu-id="c803f-152">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="c803f-153">Ověřte instalaci vytvořením aplikace `Hello World` v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="c803f-153">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="c803f-154">Nainstalujte šablony projektů.</span><span class="sxs-lookup"><span data-stu-id="c803f-154">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="c803f-155">Vytvoření nové aplikace:</span><span class="sxs-lookup"><span data-stu-id="c803f-155">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="c803f-156">Přejděte do adresáře aplikace:</span><span class="sxs-lookup"><span data-stu-id="c803f-156">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="c803f-157">Tento adresář by měl nyní obsahovat soubor s názvem `Program.qs`, což je program Q#, který definuje jednoduchou operaci pro tisk zprávy na konzolu.</span><span class="sxs-lookup"><span data-stu-id="c803f-157">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="c803f-158">Tuto šablonu můžete upravit pomocí textového editoru a přepsat ji vlastními kvantovými aplikacemi.</span><span class="sxs-lookup"><span data-stu-id="c803f-158">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="c803f-159">Spusťte program:</span><span class="sxs-lookup"><span data-stu-id="c803f-159">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="c803f-160">Měl by se vypsat následující text: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="c803f-160">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="c803f-161">Další kroky</span><span class="sxs-lookup"><span data-stu-id="c803f-161">Next steps</span></span>

<span data-ttu-id="c803f-162">Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="c803f-162">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
