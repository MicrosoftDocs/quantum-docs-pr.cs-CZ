---
title: Aktualizace sady pro vývoj pro QDK
description: 'V této části najdete popis postupu aktualizace projektů Q # a Microsoft Quantum Development Kit k aktuální verzi.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 53f72f1d49ae32a5a8572a1cf68a66a1d9b45e4a
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426912"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="5a3af-103">Aktualizace Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="5a3af-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="5a3af-104">Přečtěte si, jak aktualizovat Microsoft Quantum Development Kit (QDK) na nejnovější verzi.</span><span class="sxs-lookup"><span data-stu-id="5a3af-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="5a3af-105">V tomto článku se předpokládá, že už máte nainstalované QDK.</span><span class="sxs-lookup"><span data-stu-id="5a3af-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="5a3af-106">Pokud instalujete poprvé, přečtěte si [příručku k instalaci](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="5a3af-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="5a3af-107">Doporučujeme, abyste si zachovali aktuálnost nejnovější verze QDK.</span><span class="sxs-lookup"><span data-stu-id="5a3af-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="5a3af-108">Postupujte podle tohoto průvodce aktualizací a upgradujte na nejnovější verzi QDK.</span><span class="sxs-lookup"><span data-stu-id="5a3af-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="5a3af-109">Proces se skládá ze dvou částí:</span><span class="sxs-lookup"><span data-stu-id="5a3af-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="5a3af-110">Aktualizace existujících souborů a projektů Q # pro zarovnávání kódu pomocí aktualizované syntaxe</span><span class="sxs-lookup"><span data-stu-id="5a3af-110">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="5a3af-111">aktualizace samotného QDK pro zvolené vývojové prostředí</span><span class="sxs-lookup"><span data-stu-id="5a3af-111">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="5a3af-112">Aktualizují se projekty Q #.</span><span class="sxs-lookup"><span data-stu-id="5a3af-112">Updating Q# Projects</span></span> 

<span data-ttu-id="5a3af-113">Bez ohledu na to, jestli používáte C# nebo Python k hostování operací Q #, postupujte podle těchto pokynů a aktualizujte své projekty Q #.</span><span class="sxs-lookup"><span data-stu-id="5a3af-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="5a3af-114">Nejdřív ověřte, že máte nejnovější verzi [.NET Core SDK 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="5a3af-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="5a3af-115">Spusťte na příkazovém řádku následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="5a3af-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="5a3af-116">Ověřte, že výstup je `3.1.100` nebo vyšší.</span><span class="sxs-lookup"><span data-stu-id="5a3af-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="5a3af-117">Pokud ne, nainstalujte [nejnovější verzi](https://dotnet.microsoft.com/download) a zkuste to znovu.</span><span class="sxs-lookup"><span data-stu-id="5a3af-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="5a3af-118">Pak postupujte podle pokynů níže v závislosti na instalaci (Visual Studio, Visual Studio Code nebo přímo na příkazovém řádku).</span><span class="sxs-lookup"><span data-stu-id="5a3af-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="5a3af-119">Aktualizace projektů Q # v aplikaci Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5a3af-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="5a3af-120">Aktualizace na nejnovější verzi sady Visual Studio 2019 najdete [tady](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) pokyny.</span><span class="sxs-lookup"><span data-stu-id="5a3af-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="5a3af-121">Otevřete řešení v aplikaci Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5a3af-121">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="5a3af-122">V nabídce vyberte **sestavit**  ->  **Vyčistit řešení** .</span><span class="sxs-lookup"><span data-stu-id="5a3af-122">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="5a3af-123">V každém z vašich souborů. csproj aktualizujte cílové rozhraní na `netcoreapp3.1` (nebo `netstandard2.1` Pokud se jedná o projekt knihovny).</span><span class="sxs-lookup"><span data-stu-id="5a3af-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="5a3af-124">To znamená upravit řádky formuláře:</span><span class="sxs-lookup"><span data-stu-id="5a3af-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="5a3af-125">Další podrobnosti o určení cílových rozhraní najdete [tady](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="5a3af-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="5a3af-126">Uložit a zavřít všechny soubory ve vašem řešení</span><span class="sxs-lookup"><span data-stu-id="5a3af-126">Save and close all files in your solution</span></span>
6. <span data-ttu-id="5a3af-127">Vybrat **nástroje**  ->  **příkazového řádku**  ->  **Developer Command Prompt**</span><span class="sxs-lookup"><span data-stu-id="5a3af-127">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="5a3af-128">Pro každý projekt v řešení spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="5a3af-128">For each project in the solution, run the following command:</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="5a3af-129">Pokud vaše projekty používají jiné balíčky Microsoft. (např. Microsoft. probíhat. NUMERIC), spusťte příkaz i pro tyto.</span><span class="sxs-lookup"><span data-stu-id="5a3af-129">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="5a3af-130">Zavřete příkazový řádek a vyberte **Build**  ->  **Build** Build (nevybírejte *not* znovu sestavit řešení).</span><span class="sxs-lookup"><span data-stu-id="5a3af-130">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution)</span></span>

<span data-ttu-id="5a3af-131">Nyní můžete přeskočit k [aktualizaci rozšíření sady Visual Studio QDK](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="5a3af-131">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="5a3af-132">Aktualizace projektů Q # v Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5a3af-132">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="5a3af-133">V Visual Studio Code otevřete složku obsahující projekt, který chcete aktualizovat.</span><span class="sxs-lookup"><span data-stu-id="5a3af-133">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="5a3af-134">Vybrat **terminál**  ->  **Nový** terminál</span><span class="sxs-lookup"><span data-stu-id="5a3af-134">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="5a3af-135">Postupujte podle pokynů pro aktualizaci pomocí příkazového řádku (přímo níže).</span><span class="sxs-lookup"><span data-stu-id="5a3af-135">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="5a3af-136">Aktualizace projektů Q # pomocí příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="5a3af-136">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="5a3af-137">Přejděte do složky, která obsahuje soubor projektu.</span><span class="sxs-lookup"><span data-stu-id="5a3af-137">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="5a3af-138">Spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="5a3af-138">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="5a3af-139">V každém z vašich souborů. csproj aktualizujte cílové rozhraní na `netcoreapp3.1` (nebo `netstandard2.1` Pokud se jedná o projekt knihovny).</span><span class="sxs-lookup"><span data-stu-id="5a3af-139">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="5a3af-140">To znamená upravit řádky formuláře:</span><span class="sxs-lookup"><span data-stu-id="5a3af-140">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="5a3af-141">Další podrobnosti o určení cílových rozhraní najdete [tady](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="5a3af-141">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="5a3af-142">Spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="5a3af-142">Run the following command:</span></span>

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    <span data-ttu-id="5a3af-143">Pokud váš projekt používá jiné balíčky Microsoft. prokládání (např. Microsoft. prohodně. Numerics), spusťte příkaz i pro tyto účely.</span><span class="sxs-lookup"><span data-stu-id="5a3af-143">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="5a3af-144">Uložte a zavřete všechny soubory.</span><span class="sxs-lookup"><span data-stu-id="5a3af-144">Save and close all files.</span></span>
6. <span data-ttu-id="5a3af-145">Opakujte 1-4 pro každou závislost projektu a pak přejděte zpátky do složky, která obsahuje váš hlavní projekt, a spusťte:</span><span class="sxs-lookup"><span data-stu-id="5a3af-145">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="5a3af-146">Když se teď aktualizují projekty Q #, aktualizujte QDK sám podle pokynů níže.</span><span class="sxs-lookup"><span data-stu-id="5a3af-146">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="5a3af-147">Aktualizace QDK</span><span class="sxs-lookup"><span data-stu-id="5a3af-147">Updating the QDK</span></span>

<span data-ttu-id="5a3af-148">Proces aktualizace QDK se liší v závislosti na vašem vývojovém jazyce a prostředí.</span><span class="sxs-lookup"><span data-stu-id="5a3af-148">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="5a3af-149">Níže vyberte vývojové prostředí.</span><span class="sxs-lookup"><span data-stu-id="5a3af-149">Select your development environment below.</span></span>

* [<span data-ttu-id="5a3af-150">Python: aktualizace rozšíření SWEETIQ #</span><span class="sxs-lookup"><span data-stu-id="5a3af-150">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="5a3af-151">Jupyter poznámkové bloky: aktualizace rozšíření SWEETIQ #</span><span class="sxs-lookup"><span data-stu-id="5a3af-151">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="5a3af-152">Visual Studio: aktualizace rozšíření QDK</span><span class="sxs-lookup"><span data-stu-id="5a3af-152">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="5a3af-153">VS Code: aktualizace rozšíření QDK</span><span class="sxs-lookup"><span data-stu-id="5a3af-153">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="5a3af-154">Příkazový řádek a C#: aktualizace šablon projektů</span><span class="sxs-lookup"><span data-stu-id="5a3af-154">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="5a3af-155">Aktualizace SWEETIQ # pro Python</span><span class="sxs-lookup"><span data-stu-id="5a3af-155">Update IQ# for Python</span></span>

1. <span data-ttu-id="5a3af-156">Aktualizace `iqsharp` jádra</span><span class="sxs-lookup"><span data-stu-id="5a3af-156">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="5a3af-157">Ověření `iqsharp` verze</span><span class="sxs-lookup"><span data-stu-id="5a3af-157">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="5a3af-158">Měl by se zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="5a3af-158">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="5a3af-159">Nedělejte si starosti `iqsharp` , pokud je vaše verze vyšší, měla by odpovídat [nejnovější verzi](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="5a3af-159">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="5a3af-160">Aktualizace `qsharp` balíčku</span><span class="sxs-lookup"><span data-stu-id="5a3af-160">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="5a3af-161">Ověření `qsharp` verze</span><span class="sxs-lookup"><span data-stu-id="5a3af-161">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="5a3af-162">Měl by se zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="5a3af-162">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="5a3af-163">Z umístění vašich souborů spusťte následující příkaz. `.qs`</span><span class="sxs-lookup"><span data-stu-id="5a3af-163">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="5a3af-164">Teď můžete pomocí aktualizované verze QDK spouštět stávající programy pro užívání.</span><span class="sxs-lookup"><span data-stu-id="5a3af-164">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="5a3af-165">Aktualizace SWEETIQ # pro notebooky Jupyter</span><span class="sxs-lookup"><span data-stu-id="5a3af-165">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="5a3af-166">Aktualizace `iqsharp` jádra</span><span class="sxs-lookup"><span data-stu-id="5a3af-166">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="5a3af-167">Ověření `iqsharp` verze</span><span class="sxs-lookup"><span data-stu-id="5a3af-167">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="5a3af-168">Výstup by měl vypadat přibližně takto:</span><span class="sxs-lookup"><span data-stu-id="5a3af-168">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="5a3af-169">Nedělejte si starosti `iqsharp` , pokud je vaše verze vyšší, měla by odpovídat [nejnovější verzi](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="5a3af-169">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="5a3af-170">Z buňky v Jupyter Notebook spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="5a3af-170">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="5a3af-171">Teď můžete otevřít existující Poznámkový blok Jupyter a spustit ho s aktualizovaným QDK.</span><span class="sxs-lookup"><span data-stu-id="5a3af-171">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="5a3af-172">Aktualizovat rozšíření sady Visual Studio QDK</span><span class="sxs-lookup"><span data-stu-id="5a3af-172">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="5a3af-173">Aktualizace rozšíření Q # Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5a3af-173">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="5a3af-174">Visual Studio vás vyzve, abyste přijali aktualizace [rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) .</span><span class="sxs-lookup"><span data-stu-id="5a3af-174">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="5a3af-175">Přijmout aktualizaci</span><span class="sxs-lookup"><span data-stu-id="5a3af-175">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a3af-176">Šablony projektu jsou aktualizovány pomocí rozšíření.</span><span class="sxs-lookup"><span data-stu-id="5a3af-176">The project templates are updated with the extension.</span></span> <span data-ttu-id="5a3af-177">Aktualizované šablony se vztahují pouze na nově vytvořené projekty.</span><span class="sxs-lookup"><span data-stu-id="5a3af-177">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="5a3af-178">Kód pro existující projekty není aktualizován při aktualizaci rozšíření.</span><span class="sxs-lookup"><span data-stu-id="5a3af-178">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="5a3af-179">Aktualizovat rozšíření VS Code QDK</span><span class="sxs-lookup"><span data-stu-id="5a3af-179">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="5a3af-180">Aktualizace rozšíření VS Code pro všechna pole</span><span class="sxs-lookup"><span data-stu-id="5a3af-180">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="5a3af-181">Restartovat VS Code</span><span class="sxs-lookup"><span data-stu-id="5a3af-181">Restart VS Code</span></span>
    - <span data-ttu-id="5a3af-182">Přejít na kartu **rozšíření**</span><span class="sxs-lookup"><span data-stu-id="5a3af-182">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="5a3af-183">Vyberte **Microsoft Quantum Development Kit pro rozšíření Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="5a3af-183">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="5a3af-184">Načíst znovu rozšíření</span><span class="sxs-lookup"><span data-stu-id="5a3af-184">Reload the extension</span></span>

2. <span data-ttu-id="5a3af-185">Aktualizace šablon projektů pro každé z nich:</span><span class="sxs-lookup"><span data-stu-id="5a3af-185">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="5a3af-186">Přejít na **View**  ->  **paletu příkazů** zobrazení</span><span class="sxs-lookup"><span data-stu-id="5a3af-186">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="5a3af-187">Vyberte **Q #: Instalace šablon projektů**</span><span class="sxs-lookup"><span data-stu-id="5a3af-187">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="5a3af-188">Po několika sekundách byste měli obdržet místní nabídku potvrzující, že se šablony projektů úspěšně nainstalovaly.</span><span class="sxs-lookup"><span data-stu-id="5a3af-188">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="5a3af-189">C#, použití `dotnet` nástroje příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="5a3af-189">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="5a3af-190">Aktualizace šablon projektů pro každý produkt pro .NET</span><span class="sxs-lookup"><span data-stu-id="5a3af-190">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```