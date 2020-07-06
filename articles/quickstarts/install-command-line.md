---
title: Vývoj aplikací příkazového řádku v Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 15015d1673f47faf5a13dde516f834916b4319d6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884281"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="fdf93-102">Vývoj aplikací příkazového řádku v Q#</span><span class="sxs-lookup"><span data-stu-id="fdf93-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="fdf93-103">Programy Q# se dají spouštět samostatně, bez ovladače v hostitelském jazyce jako C#, F# nebo Python.</span><span class="sxs-lookup"><span data-stu-id="fdf93-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fdf93-104">Požadavky</span><span class="sxs-lookup"><span data-stu-id="fdf93-104">Prerequisites</span></span>

- [<span data-ttu-id="fdf93-105">.NET Core SDK 3.1 nebo novější</span><span class="sxs-lookup"><span data-stu-id="fdf93-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="fdf93-106">Instalace</span><span class="sxs-lookup"><span data-stu-id="fdf93-106">Installation</span></span>

<span data-ttu-id="fdf93-107">I když můžete aplikaci příkazového řádku Q# sestavit v jakémkoli integrovaném vývojovém prostředí, doporučujeme použít Visual Studio Code (VS Code) nebo Visual Studio IDE.</span><span class="sxs-lookup"><span data-stu-id="fdf93-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="fdf93-108">Vývoj v těchto prostředích poskytuje bohaté funkce rozšíření QDK, mezi které patří upozornění, zvýrazňování syntaxe, šablony projektů a další.</span><span class="sxs-lookup"><span data-stu-id="fdf93-108">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="fdf93-109">Konfigurace VS Code:</span><span class="sxs-lookup"><span data-stu-id="fdf93-109">To configure VS Code:</span></span>

1. <span data-ttu-id="fdf93-110">Stáhněte si a nainstalujte [VS Code](https://code.visualstudio.com/download) (Windows, Linux a Mac).</span><span class="sxs-lookup"><span data-stu-id="fdf93-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="fdf93-111">Nainstalujte [Microsoft QDK pro VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="fdf93-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="fdf93-112">Konfigurace sady Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="fdf93-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="fdf93-113">Stáhněte si a nainstalujte [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 nebo novější s podporou multiplatformního vývoje .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fdf93-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="fdf93-114">Stáhněte si a nainstalujte [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="fdf93-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="fdf93-115">Pokud chcete nainstalovat QDK pro jiné prostředí, zadejte do příkazového řádku:</span><span class="sxs-lookup"><span data-stu-id="fdf93-115">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a><span data-ttu-id="fdf93-116">Vývoj s využitím Q#</span><span class="sxs-lookup"><span data-stu-id="fdf93-116">Develop with Q#</span></span>

<span data-ttu-id="fdf93-117">Postupujte podle pokynů na kartě odpovídající vašemu prostředí.</span><span class="sxs-lookup"><span data-stu-id="fdf93-117">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="fdf93-118">VS Code</span><span class="sxs-lookup"><span data-stu-id="fdf93-118">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="fdf93-119">Nainstalujte šablony projektů Q#:</span><span class="sxs-lookup"><span data-stu-id="fdf93-119">Install the Q# project templates:</span></span>

1. <span data-ttu-id="fdf93-120">Otevřete VS Code.</span><span class="sxs-lookup"><span data-stu-id="fdf93-120">Open VS Code.</span></span>
2. <span data-ttu-id="fdf93-121">Klikněte na **Zobrazit** -> **Paleta příkazů**.</span><span class="sxs-lookup"><span data-stu-id="fdf93-121">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="fdf93-122">Vyberte **Q#: Instalovat šablony projektů**.</span><span class="sxs-lookup"><span data-stu-id="fdf93-122">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="fdf93-123">Když se zobrazí zpráva **Šablony projektů byly úspěšně nainstalovány**, sada QDK je připravena na vývoj vašich vlastních knihoven a aplikací.</span><span class="sxs-lookup"><span data-stu-id="fdf93-123">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="fdf93-124">Vytvoření nového projektu:</span><span class="sxs-lookup"><span data-stu-id="fdf93-124">To create a new project:</span></span>

1. <span data-ttu-id="fdf93-125">Klikněte na **Zobrazení** -> **Paleta příkazů** a vyberte **Q#: Vytvořit nový projekt**.</span><span class="sxs-lookup"><span data-stu-id="fdf93-125">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="fdf93-126">Klikněte na **Samostatná konzolová aplikace**.</span><span class="sxs-lookup"><span data-stu-id="fdf93-126">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="fdf93-127">Přejděte do umístění, kam chcete projekt uložit, a klikněte na **Vytvořit projekt**.</span><span class="sxs-lookup"><span data-stu-id="fdf93-127">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="fdf93-128">Po úspěšném vytvoření projektu klikněte na **Otevřít nový projekt...** v pravém dolním rohu.</span><span class="sxs-lookup"><span data-stu-id="fdf93-128">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="fdf93-129">Prozkoumejte projekt.</span><span class="sxs-lookup"><span data-stu-id="fdf93-129">Inspect the project.</span></span> <span data-ttu-id="fdf93-130">Měl by se zobrazit zdrojový soubor s názvem `Program.qs`, což je program Q#, který definuje jednoduchou operaci pro tisk zprávy na konzolu.</span><span class="sxs-lookup"><span data-stu-id="fdf93-130">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="fdf93-131">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="fdf93-131">To run the application:</span></span>
1. <span data-ttu-id="fdf93-132">Klikněte na **Terminál** -> **Nový Terminál**.</span><span class="sxs-lookup"><span data-stu-id="fdf93-132">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="fdf93-133">Na příkazovém řádku terminálu zadejte `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="fdf93-133">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="fdf93-134">V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="fdf93-134">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="fdf93-135">Rozšíření Q# pro VS Code aktuálně nepodporuje pracovní prostory s více kořenovými složkami.</span><span class="sxs-lookup"><span data-stu-id="fdf93-135">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="fdf93-136">Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.</span><span class="sxs-lookup"><span data-stu-id="fdf93-136">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="fdf93-137">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fdf93-137">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="fdf93-138">Ověřte instalaci sady Visual Studio vytvořením aplikace `Hello World` v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="fdf93-138">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="fdf93-139">Vytvoření nové aplikace v jazyce Q#:</span><span class="sxs-lookup"><span data-stu-id="fdf93-139">To create a new Q# application:</span></span>
1. <span data-ttu-id="fdf93-140">Otevřete Visual Studio a klikněte na **Soubor** -> **Nový** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="fdf93-140">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="fdf93-141">Do vyhledávacího pole zadejte `Q#`, vyberte **Aplikace Q#** a klikněte na **Další**.</span><span class="sxs-lookup"><span data-stu-id="fdf93-141">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="fdf93-142">Zadejte název a umístění vaší aplikace a klikněte na **Vytvořit**.</span><span class="sxs-lookup"><span data-stu-id="fdf93-142">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="fdf93-143">Prozkoumejte projekt.</span><span class="sxs-lookup"><span data-stu-id="fdf93-143">Inspect the project.</span></span> <span data-ttu-id="fdf93-144">Měl by se zobrazit zdrojový soubor s názvem `Program.qs`, což je program Q#, který definuje jednoduchou operaci pro tisk zprávy na konzolu.</span><span class="sxs-lookup"><span data-stu-id="fdf93-144">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="fdf93-145">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="fdf93-145">To run the application:</span></span>
1. <span data-ttu-id="fdf93-146">Vyberte **Ladit** -> **Spustit bez ladění**.</span><span class="sxs-lookup"><span data-stu-id="fdf93-146">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="fdf93-147">V okně konzoly by se měl zobrazit text `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="fdf93-147">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="fdf93-148">Pokud máte v jednom řešení sady Visual Studio více projektů, všechny projekty obsažené v řešení se musí nacházet ve stejné složce jako řešení nebo v jedné z jejích podsložek.</span><span class="sxs-lookup"><span data-stu-id="fdf93-148">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="fdf93-149">Další editory s příkazovým řádkem</span><span class="sxs-lookup"><span data-stu-id="fdf93-149">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="fdf93-150">Ověřte instalaci vytvořením aplikace `Hello World` v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="fdf93-150">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="fdf93-151">Vytvoření nové aplikace:</span><span class="sxs-lookup"><span data-stu-id="fdf93-151">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

2. <span data-ttu-id="fdf93-152">Přejděte do adresáře aplikace:</span><span class="sxs-lookup"><span data-stu-id="fdf93-152">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="fdf93-153">Tento adresář by měl nyní obsahovat soubor s názvem `Program.qs`, což je program Q#, který definuje jednoduchou operaci pro tisk zprávy na konzolu.</span><span class="sxs-lookup"><span data-stu-id="fdf93-153">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="fdf93-154">Tuto šablonu můžete upravit pomocí textového editoru a přepsat ji vlastními kvantovými aplikacemi.</span><span class="sxs-lookup"><span data-stu-id="fdf93-154">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

3. <span data-ttu-id="fdf93-155">Spusťte program:</span><span class="sxs-lookup"><span data-stu-id="fdf93-155">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

4. <span data-ttu-id="fdf93-156">Měl by se vypsat následující text: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="fdf93-156">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="fdf93-157">Další kroky</span><span class="sxs-lookup"><span data-stu-id="fdf93-157">Next steps</span></span>

<span data-ttu-id="fdf93-158">Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="fdf93-158">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
