---
title: 'Spustit programy Q # bez ovladače a jazyka hostitele'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706797"
---
# <a name="q-command-line-applications"></a><span data-ttu-id="d9c9d-102">Aplikace příkazového řádku Q #</span><span class="sxs-lookup"><span data-stu-id="d9c9d-102">Q# Command Line Applications</span></span>

<span data-ttu-id="d9c9d-103">Programy Q # se dají spouštět samostatně, bez ovladače v hostitelském jazyce, jako je C#, F # nebo Python.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="d9c9d-104">Požadavky</span><span class="sxs-lookup"><span data-stu-id="d9c9d-104">Pre-requisites</span></span>

- [<span data-ttu-id="d9c9d-105">.NET Core SDK 3,1 nebo novější</span><span class="sxs-lookup"><span data-stu-id="d9c9d-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="d9c9d-106">Instalace</span><span class="sxs-lookup"><span data-stu-id="d9c9d-106">Installation</span></span>

<span data-ttu-id="d9c9d-107">I když můžete sestavovat aplikace příkazového řádku Q # v jakémkoli integrovaném vývojovém prostředí, důrazně doporučujeme použít Visual Studio Code (VS Code) nebo Visual Studio IDE pro vaše aplikace Q #.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-107">While you can build Q# command line applications in any IDE, we highly recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="d9c9d-108">Pomocí VS Code nebo Visual studia a rozšíření QDK Visual Studio Code získáte přístup k rozsáhlejším funkcím.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-108">By using VS Code or Visual Studio and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

- <span data-ttu-id="d9c9d-109">Nainstalovat [vs Code](https://code.visualstudio.com/download) (Windows, Linux a Mac)</span><span class="sxs-lookup"><span data-stu-id="d9c9d-109">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
- <span data-ttu-id="d9c9d-110">Nainstalujte [rozšíření QDK pro vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) nebo</span><span class="sxs-lookup"><span data-stu-id="d9c9d-110">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) OR</span></span>
- <span data-ttu-id="d9c9d-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 s povolenými úlohami vývoje pro různé platformy pomocí rozhraní .NET Core</span><span class="sxs-lookup"><span data-stu-id="d9c9d-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>
- <span data-ttu-id="d9c9d-112">Stažení a instalace [rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="d9c9d-112">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="d9c9d-113">Vývoj pomocí Q # pomocí VS Code</span><span class="sxs-lookup"><span data-stu-id="d9c9d-113">Develop with Q# using VS Code</span></span>

<span data-ttu-id="d9c9d-114">Nainstalujte šablony kvantového projektu:</span><span class="sxs-lookup"><span data-stu-id="d9c9d-114">Install the Quantum project templates:</span></span>

- <span data-ttu-id="d9c9d-115">Přejít na **View** -> **paletu příkazů** zobrazení</span><span class="sxs-lookup"><span data-stu-id="d9c9d-115">Go to **View** -> **Command Palette**</span></span>
- <span data-ttu-id="d9c9d-116">Vyberte **Q #: Instalace šablon projektů**</span><span class="sxs-lookup"><span data-stu-id="d9c9d-116">Select **Q#: Install project templates**</span></span>

<span data-ttu-id="d9c9d-117">Teď máte sadu Quantum Development Kit nainstalovanou a připravenou k používání ve vašich vlastních aplikacích a knihovnách.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-117">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>
- <span data-ttu-id="d9c9d-118">Vytvořte nový projekt:</span><span class="sxs-lookup"><span data-stu-id="d9c9d-118">Create a new project:</span></span>
  - <span data-ttu-id="d9c9d-119">Přejít na **View** -> **paletu příkazů** zobrazení</span><span class="sxs-lookup"><span data-stu-id="d9c9d-119">Go to **View** -> **Command Palette**</span></span>
  - <span data-ttu-id="d9c9d-120">Vyberte **Q #: vytvořit nový projekt.**</span><span class="sxs-lookup"><span data-stu-id="d9c9d-120">Select **Q#: Create New Project**</span></span>
  - <span data-ttu-id="d9c9d-121">Vybrat **samostatnou konzolovou aplikaci**</span><span class="sxs-lookup"><span data-stu-id="d9c9d-121">Select **Standalone console application**</span></span>
  - <span data-ttu-id="d9c9d-122">Přejděte do umístění v systému souborů, ve kterém chcete aplikaci vytvořit.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-122">Navigate to the location on the file system where you would like to create the application</span></span>
  - <span data-ttu-id="d9c9d-123">Po vytvoření projektu klikněte na tlačítko **Otevřít nový projekt**.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-123">Click on the **Open new project...** button, once the project has been created</span></span>
        
- <span data-ttu-id="d9c9d-124">Prozkoumejte projekt.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-124">Inspect the project</span></span>
  - <span data-ttu-id="d9c9d-125">Měl by se zobrazit, že soubor `Program.qs` nazvaný byl vytvořen, což je program Q #, který definuje jednoduchou operaci pro tisk zprávy do konzoly.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-125">You should see that a file called `Program.qs` created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="d9c9d-126">Spusťte aplikaci:</span><span class="sxs-lookup"><span data-stu-id="d9c9d-126">Run the application:</span></span>
  - <span data-ttu-id="d9c9d-127">Přejít na **terminál** -> **nový terminál**</span><span class="sxs-lookup"><span data-stu-id="d9c9d-127">Go to **Terminal** -> **New Terminal**</span></span>
  - <span data-ttu-id="d9c9d-128">Napište`dotnet run`</span><span class="sxs-lookup"><span data-stu-id="d9c9d-128">Enter `dotnet run`</span></span>
  - <span data-ttu-id="d9c9d-129">V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="d9c9d-129">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="d9c9d-130">Rozšíření Visual Studio Code aktuálně nepodporuje pracovní prostory s více kořenovými složkami.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-130">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="d9c9d-131">Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-131">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="d9c9d-132">Vývoj pomocí Q # pomocí sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d9c9d-132">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="d9c9d-133">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-133">Verify the installation by creating a `Hello World` application</span></span>

- <span data-ttu-id="d9c9d-134">Vytvořte novou aplikaci v jazyku Q#.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-134">Create a new Q# application</span></span>
  - <span data-ttu-id="d9c9d-135">Přejít na **soubor** -> **Nový** -> **projekt**</span><span class="sxs-lookup"><span data-stu-id="d9c9d-135">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="d9c9d-136">Do vyhledávacího pole zadejte `Q#`.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-136">Type `Q#` in the search box</span></span>
  - <span data-ttu-id="d9c9d-137">Vyberte **Aplikace Q#**.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-137">Select **Q# Application**</span></span>
  - <span data-ttu-id="d9c9d-138">Vybrat **Další**</span><span class="sxs-lookup"><span data-stu-id="d9c9d-138">Select **Next**</span></span>
  - <span data-ttu-id="d9c9d-139">Vyberte název a umístění aplikace.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-139">Choose a name and location for your application</span></span>
  - <span data-ttu-id="d9c9d-140">Vyberte **vytvořit** .</span><span class="sxs-lookup"><span data-stu-id="d9c9d-140">Select **Create**</span></span>

- <span data-ttu-id="d9c9d-141">Prozkoumejte projekt.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-141">Inspect the project</span></span>
  - <span data-ttu-id="d9c9d-142">Měl by se zobrazit, že byl `Program.qs` vytvořen soubor s názvem, což je program Q #, který definuje jednoduchou operaci pro tisk zprávy do konzoly.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-142">You should see that a file called `Program.qs` has been created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="d9c9d-143">Spuštění aplikace</span><span class="sxs-lookup"><span data-stu-id="d9c9d-143">Run the application</span></span>
  - <span data-ttu-id="d9c9d-144">Vyberte **ladit** -> **Spustit bez ladění**</span><span class="sxs-lookup"><span data-stu-id="d9c9d-144">Select **Debug** -> **Start Without Debugging**</span></span>
  - <span data-ttu-id="d9c9d-145">V okně konzoly by se měl zobrazit text `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-145">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="d9c9d-146">Pokud řešení sady Visual Studio obsahuje více projektů, musí se všechny projekty obsažené v řešení nacházet ve stejné složce jako řešení nebo v jedné z jejích podsložek.</span><span class="sxs-lookup"><span data-stu-id="d9c9d-146">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  


## <a name="whats-next"></a><span data-ttu-id="d9c9d-147">Co dále?</span><span class="sxs-lookup"><span data-stu-id="d9c9d-147">What's next?</span></span>

<span data-ttu-id="d9c9d-148">Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="d9c9d-148">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
