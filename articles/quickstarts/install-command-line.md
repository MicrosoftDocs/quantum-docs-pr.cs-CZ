---
title: Vývoj aplikací příkazového řádku v Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274064"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="154d5-102">Vývoj aplikací příkazového řádku v Q#</span><span class="sxs-lookup"><span data-stu-id="154d5-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="154d5-103">Programy Q# se dají spouštět samostatně, bez ovladače v hostitelském jazyce jako C#, F# nebo Python.</span><span class="sxs-lookup"><span data-stu-id="154d5-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="154d5-104">Požadavky</span><span class="sxs-lookup"><span data-stu-id="154d5-104">Prerequisites</span></span>

- [<span data-ttu-id="154d5-105">.NET Core SDK 3.1 nebo novější</span><span class="sxs-lookup"><span data-stu-id="154d5-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="154d5-106">Instalace</span><span class="sxs-lookup"><span data-stu-id="154d5-106">Installation</span></span>

<span data-ttu-id="154d5-107">I když můžete aplikaci příkazového řádku Q# sestavit v jakémkoli integrovaném vývojovém prostředí, doporučujeme použít Visual Studio Code (VS Code) nebo Visual Studio IDE.</span><span class="sxs-lookup"><span data-stu-id="154d5-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="154d5-108">Vývoj v těchto nástrojích poskytuje přístup k bohaté paletě funkcí.</span><span class="sxs-lookup"><span data-stu-id="154d5-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="154d5-109">Konfigurace VS Code:</span><span class="sxs-lookup"><span data-stu-id="154d5-109">To configure VS Code:</span></span>

1. <span data-ttu-id="154d5-110">Stáhněte si a nainstalujte [VS Code](https://code.visualstudio.com/download) (Windows, Linux a Mac).</span><span class="sxs-lookup"><span data-stu-id="154d5-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="154d5-111">Nainstalujte [Microsoft QDK pro VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="154d5-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="154d5-112">Konfigurace sady Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="154d5-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="154d5-113">Stáhněte si a nainstalujte [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 nebo novější s podporou multiplatformního vývoje .NET Core.</span><span class="sxs-lookup"><span data-stu-id="154d5-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="154d5-114">Stáhněte si a nainstalujte [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="154d5-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="154d5-115">Vývoj v jazyce Q# s využitím VS Code</span><span class="sxs-lookup"><span data-stu-id="154d5-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="154d5-116">Nainstalujte šablony projektů Q#:</span><span class="sxs-lookup"><span data-stu-id="154d5-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="154d5-117">Otevřete VS Code.</span><span class="sxs-lookup"><span data-stu-id="154d5-117">Open VS Code.</span></span>
2. <span data-ttu-id="154d5-118">Klikněte na **Zobrazit** -> **Paleta příkazů**.</span><span class="sxs-lookup"><span data-stu-id="154d5-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="154d5-119">Vyberte **Q#: Instalovat šablony projektů**.</span><span class="sxs-lookup"><span data-stu-id="154d5-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="154d5-120">Když se zobrazí zpráva **Šablony projektů byly úspěšně nainstalovány**, sada QDK je připravena na vývoj vašich vlastních knihoven a aplikací.</span><span class="sxs-lookup"><span data-stu-id="154d5-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="154d5-121">Vytvoření nového projektu:</span><span class="sxs-lookup"><span data-stu-id="154d5-121">To create a new project:</span></span>

1. <span data-ttu-id="154d5-122">Klikněte na **Zobrazení** -> **Paleta příkazů** a vyberte **Q#: Vytvořit nový projekt**.</span><span class="sxs-lookup"><span data-stu-id="154d5-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="154d5-123">Klikněte na **Samostatná konzolová aplikace**.</span><span class="sxs-lookup"><span data-stu-id="154d5-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="154d5-124">Přejděte do umístění, kam chcete projekt uložit, a klikněte na **Vytvořit projekt**.</span><span class="sxs-lookup"><span data-stu-id="154d5-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="154d5-125">Po úspěšném vytvoření projektu klikněte na **Otevřít nový projekt...** v pravém dolním rohu.</span><span class="sxs-lookup"><span data-stu-id="154d5-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="154d5-126">Prozkoumejte projekt.</span><span class="sxs-lookup"><span data-stu-id="154d5-126">Inspect the project.</span></span> <span data-ttu-id="154d5-127">Měl by se zobrazit zdrojový soubor s názvem `Program.qs`, což je program Q#, který definuje jednoduchou operaci pro tisk zprávy na konzolu.</span><span class="sxs-lookup"><span data-stu-id="154d5-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="154d5-128">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="154d5-128">To run the application:</span></span>
1. <span data-ttu-id="154d5-129">Klikněte na **Terminál** -> **Nový Terminál**.</span><span class="sxs-lookup"><span data-stu-id="154d5-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="154d5-130">Na příkazovém řádku terminálu zadejte `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="154d5-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="154d5-131">V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="154d5-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="154d5-132">Rozšíření Q# pro VS Code aktuálně nepodporuje pracovní prostory s více kořenovými složkami.</span><span class="sxs-lookup"><span data-stu-id="154d5-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="154d5-133">Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.</span><span class="sxs-lookup"><span data-stu-id="154d5-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="154d5-134">Vývoj v Q# v sadě Visual Studio</span><span class="sxs-lookup"><span data-stu-id="154d5-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="154d5-135">Ověřte instalaci sady Visual Studio vytvořením aplikace `Hello World` v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="154d5-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="154d5-136">Vytvoření nové aplikace v jazyce Q#:</span><span class="sxs-lookup"><span data-stu-id="154d5-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="154d5-137">Otevřete Visual Studio a klikněte na **Soubor** -> **Nový** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="154d5-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="154d5-138">Do vyhledávacího pole zadejte `Q#`, vyberte **Aplikace Q#** a klikněte na **Další**.</span><span class="sxs-lookup"><span data-stu-id="154d5-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="154d5-139">Zadejte název a umístění vaší aplikace a klikněte na **Vytvořit**.</span><span class="sxs-lookup"><span data-stu-id="154d5-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="154d5-140">Prozkoumejte projekt.</span><span class="sxs-lookup"><span data-stu-id="154d5-140">Inspect the project.</span></span> <span data-ttu-id="154d5-141">Měl by se zobrazit zdrojový soubor s názvem `Program.qs`, což je program Q#, který definuje jednoduchou operaci pro tisk zprávy na konzolu.</span><span class="sxs-lookup"><span data-stu-id="154d5-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="154d5-142">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="154d5-142">To run the application:</span></span>
1. <span data-ttu-id="154d5-143">Vyberte **Ladit** -> **Spustit bez ladění**.</span><span class="sxs-lookup"><span data-stu-id="154d5-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="154d5-144">V okně konzoly by se měl zobrazit text `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="154d5-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="154d5-145">Pokud máte v jednom řešení sady Visual Studio více projektů, všechny projekty obsažené v řešení se musí nacházet ve stejné složce jako řešení nebo v jedné z jejích podsložek.</span><span class="sxs-lookup"><span data-stu-id="154d5-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="154d5-146">Další kroky</span><span class="sxs-lookup"><span data-stu-id="154d5-146">Next steps</span></span>

<span data-ttu-id="154d5-147">Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="154d5-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
