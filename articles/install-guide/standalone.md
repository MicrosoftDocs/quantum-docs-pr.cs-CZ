---
title: 'Vývoj s aplikacemi příkazového řádku Q #'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e829862521951c50cb42eebf261c803071a95275
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426437"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="cbb8d-102">Vývoj s aplikacemi příkazového řádku Q #</span><span class="sxs-lookup"><span data-stu-id="cbb8d-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="cbb8d-103">Programy Q # se dají spouštět samostatně, bez ovladače v hostitelském jazyce, jako je C#, F # nebo Python.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="cbb8d-104">Požadavky</span><span class="sxs-lookup"><span data-stu-id="cbb8d-104">Pre-requisites</span></span>

- [<span data-ttu-id="cbb8d-105">.NET Core SDK 3,1 nebo novější</span><span class="sxs-lookup"><span data-stu-id="cbb8d-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="cbb8d-106">Instalace</span><span class="sxs-lookup"><span data-stu-id="cbb8d-106">Installation</span></span>

<span data-ttu-id="cbb8d-107">I když můžete sestavit aplikace příkazového řádku Q # v jakémkoli integrovaném vývojovém prostředí, doporučujeme pro aplikace Q # použít Visual Studio Code (VS Code) nebo Visual Studio IDE.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="cbb8d-108">Vývoj v těchto nástrojích poskytuje přístup k bohatě funkčním funkcím.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="cbb8d-109">Konfigurace VS Code:</span><span class="sxs-lookup"><span data-stu-id="cbb8d-109">To configure VS Code:</span></span>

1. <span data-ttu-id="cbb8d-110">Stáhněte a nainstalujte [vs Code](https://code.visualstudio.com/download) (Windows, Linux a Mac).</span><span class="sxs-lookup"><span data-stu-id="cbb8d-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="cbb8d-111">Nainstalujte [Microsoft QDK pro vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="cbb8d-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="cbb8d-112">Konfigurace sady Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="cbb8d-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="cbb8d-113">Stáhněte si a nainstalujte [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3 nebo novější s povolenou úlohou vývoje .NET Core pro různé platformy.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="cbb8d-114">Stáhněte a nainstalujte [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="cbb8d-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="cbb8d-115">Vývoj pomocí Q # pomocí VS Code</span><span class="sxs-lookup"><span data-stu-id="cbb8d-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="cbb8d-116">Instalace šablon projektů Q #:</span><span class="sxs-lookup"><span data-stu-id="cbb8d-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="cbb8d-117">Otevřete VS Code.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-117">Open VS Code.</span></span>
2. <span data-ttu-id="cbb8d-118">Klikněte na tlačítko **Zobrazit**  ->  **paletu příkazů**.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="cbb8d-119">Vyberte **Q #: Instalace šablon projektů**.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="cbb8d-120">Po **úspěšném dokončení instalace šablon projektů** je QDK připravený k použití s vlastními aplikacemi a knihovnami.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="cbb8d-121">Vytvoření nového projektu:</span><span class="sxs-lookup"><span data-stu-id="cbb8d-121">To create a new project:</span></span>

1. <span data-ttu-id="cbb8d-122">Klikněte na **Zobrazit**  ->  **paletu příkazů** a vyberte **Q #: vytvořit nový projekt**.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="cbb8d-123">Klikněte na **samostatná Konzolová aplikace**.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="cbb8d-124">Přejděte do umístění, kam chcete projekt uložit, a klikněte na **vytvořit projekt**.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="cbb8d-125">Po úspěšném vytvoření projektu klikněte v pravém dolním rohu na **Otevřít nový projekt...** .</span><span class="sxs-lookup"><span data-stu-id="cbb8d-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="cbb8d-126">Zkontrolujte projekt.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-126">Inspect the project.</span></span> <span data-ttu-id="cbb8d-127">Měl by se zobrazit zdrojový soubor s názvem `Program.qs` , což je program Q #, který definuje jednoduchou operaci pro tisk zprávy do konzoly.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="cbb8d-128">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="cbb8d-128">To run the application:</span></span>
1. <span data-ttu-id="cbb8d-129">Klikněte na **terminál**  ->  **nový terminál**.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="cbb8d-130">Na příkazovém řádku terminálu zadejte `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="cbb8d-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="cbb8d-131">V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="cbb8d-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="cbb8d-132">Pracovní prostory s více kořenovými složkami se v současné době rozšíření VS Code Q # nepodporují.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="cbb8d-133">Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="cbb8d-134">Vývoj pomocí Q # pomocí sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cbb8d-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="cbb8d-135">Ověřte instalaci sady Visual Studio vytvořením aplikace Q # `Hello World` .</span><span class="sxs-lookup"><span data-stu-id="cbb8d-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="cbb8d-136">Vytvoření nové aplikace Q #:</span><span class="sxs-lookup"><span data-stu-id="cbb8d-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="cbb8d-137">Otevřete Visual Studio a klikněte na **soubor**  ->  **Nový**  ->  **projekt**.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="cbb8d-138">`Q#`Do vyhledávacího pole zadejte, vyberte **Q # Application** a klikněte na **Další**.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="cbb8d-139">Zadejte název a umístění vaší aplikace a klikněte na **vytvořit**.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="cbb8d-140">Zkontrolujte projekt.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-140">Inspect the project.</span></span> <span data-ttu-id="cbb8d-141">Měl by se zobrazit zdrojový soubor s názvem `Program.qs` , což je program Q #, který definuje jednoduchou operaci pro tisk zprávy do konzoly.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="cbb8d-142">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="cbb8d-142">To run the application:</span></span>
1. <span data-ttu-id="cbb8d-143">Vyberte **ladit**  ->  **Spustit bez ladění**.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="cbb8d-144">V okně konzoly by se měl zobrazit text `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="cbb8d-145">Pokud máte více projektů v rámci jednoho řešení sady Visual Studio, všechny projekty, které jsou obsaženy v řešení, musí být ve stejné složce jako řešení nebo v jedné z jejích podsložek.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="cbb8d-146">Další kroky</span><span class="sxs-lookup"><span data-stu-id="cbb8d-146">Next steps</span></span>

<span data-ttu-id="cbb8d-147">Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="cbb8d-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
