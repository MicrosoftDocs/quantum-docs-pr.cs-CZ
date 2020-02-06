---
title: Informace o tom, jak aktualizovat Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: f19285ae0e008b3460d06430a236f098d716e268
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036303"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="89cd9-102">Aktualizace Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="89cd9-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="89cd9-103">Přečtěte si, jak aktualizovat Microsoft Quantum Development Kit (QDK) na nejnovější verzi.</span><span class="sxs-lookup"><span data-stu-id="89cd9-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="89cd9-104">V tomto článku se předpokládá, že už máte nainstalované QDK.</span><span class="sxs-lookup"><span data-stu-id="89cd9-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="89cd9-105">Pokud instalujete poprvé, přečtěte si [příručku k instalaci](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="89cd9-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="89cd9-106">Doporučujeme, abyste si zachovali aktuálnost nejnovější verze QDK.</span><span class="sxs-lookup"><span data-stu-id="89cd9-106">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="89cd9-107">Postupujte podle tohoto průvodce aktualizací a upgradujte na nejnovější verzi QDK.</span><span class="sxs-lookup"><span data-stu-id="89cd9-107">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="89cd9-108">Proces se skládá ze dvou částí:</span><span class="sxs-lookup"><span data-stu-id="89cd9-108">The process consists of two parts:</span></span>
1. <span data-ttu-id="89cd9-109">Aktualizace existujících souborů a projektů Q # pro zarovnávání kódu pomocí aktualizované syntaxe</span><span class="sxs-lookup"><span data-stu-id="89cd9-109">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="89cd9-110">aktualizace samotného QDK pro zvolené vývojové prostředí</span><span class="sxs-lookup"><span data-stu-id="89cd9-110">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="89cd9-111">Aktualizují se projekty Q #.</span><span class="sxs-lookup"><span data-stu-id="89cd9-111">Updating Q# Projects</span></span> 

<span data-ttu-id="89cd9-112">Bez ohledu na to, jestli používáte C# nebo Python k hostování operací q #, postupujte podle těchto pokynů a aktualizujte své projekty q #.</span><span class="sxs-lookup"><span data-stu-id="89cd9-112">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="89cd9-113">Nejdřív ověřte, že máte nejnovější verzi [.NET Core SDK 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="89cd9-113">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="89cd9-114">Spusťte na příkazovém řádku následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="89cd9-114">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="89cd9-115">Ověřte, že výstup je `3.1.100` nebo vyšší.</span><span class="sxs-lookup"><span data-stu-id="89cd9-115">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="89cd9-116">Pokud ne, nainstalujte [nejnovější verzi](https://dotnet.microsoft.com/download) a zkuste to znovu.</span><span class="sxs-lookup"><span data-stu-id="89cd9-116">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="89cd9-117">Pak postupujte podle pokynů níže v závislosti na instalaci (Visual Studio, Visual Studio Code nebo přímo na příkazovém řádku).</span><span class="sxs-lookup"><span data-stu-id="89cd9-117">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="89cd9-118">Aktualizace projektů Q # v aplikaci Visual Studio</span><span class="sxs-lookup"><span data-stu-id="89cd9-118">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="89cd9-119">Aktualizace na nejnovější verzi sady Visual Studio 2019 najdete [tady](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) pokyny.</span><span class="sxs-lookup"><span data-stu-id="89cd9-119">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="89cd9-120">Otevřete řešení v aplikaci Visual Studio</span><span class="sxs-lookup"><span data-stu-id="89cd9-120">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="89cd9-121">V nabídce vyberte **sestavení** -> **Vyčistit řešení** .</span><span class="sxs-lookup"><span data-stu-id="89cd9-121">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="89cd9-122">V každém z vašich souborů. csproj aktualizujte cílovou verzi rozhraní .NET Framework na `netcoreapp3.0` (nebo `netstandard2.1`, pokud se jedná o projekt knihovny).</span><span class="sxs-lookup"><span data-stu-id="89cd9-122">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="89cd9-123">To znamená upravit řádky formuláře:</span><span class="sxs-lookup"><span data-stu-id="89cd9-123">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    <span data-ttu-id="89cd9-124">Další podrobnosti o určení cílových rozhraní najdete [tady](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="89cd9-124">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="89cd9-125">Uložit a zavřít všechny soubory ve vašem řešení</span><span class="sxs-lookup"><span data-stu-id="89cd9-125">Save and close all files in your solution</span></span>
6. <span data-ttu-id="89cd9-126">Vyberte **nástroje** -> **příkazového řádku** -> **Developer Command Prompt**</span><span class="sxs-lookup"><span data-stu-id="89cd9-126">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="89cd9-127">Pro každý projekt v řešení spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="89cd9-127">For each project in the solution, run the following command:</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="89cd9-128">Pokud vaše projekty používají jiné balíčky Microsoft. (např. Microsoft. probíhat. NUMERIC), spusťte příkaz i pro tyto.</span><span class="sxs-lookup"><span data-stu-id="89cd9-128">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="89cd9-129">Zavřete příkazový řádek a vyberte **sestavit** -> **Sestavit řešení** ( *nevybírejte znovu* sestavit řešení).</span><span class="sxs-lookup"><span data-stu-id="89cd9-129">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution)</span></span>

<span data-ttu-id="89cd9-130">Nyní můžete přeskočit k [aktualizaci rozšíření sady Visual Studio QDK](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="89cd9-130">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="89cd9-131">Aktualizace projektů Q # v Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="89cd9-131">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="89cd9-132">V Visual Studio Code otevřete složku obsahující projekt, který chcete aktualizovat.</span><span class="sxs-lookup"><span data-stu-id="89cd9-132">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="89cd9-133">Výběr **terminálu** -> **nového terminálu**</span><span class="sxs-lookup"><span data-stu-id="89cd9-133">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="89cd9-134">Postupujte podle pokynů pro aktualizaci pomocí příkazového řádku (přímo níže).</span><span class="sxs-lookup"><span data-stu-id="89cd9-134">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="89cd9-135">Aktualizace projektů Q # pomocí příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="89cd9-135">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="89cd9-136">Přejděte do složky, která obsahuje soubor projektu.</span><span class="sxs-lookup"><span data-stu-id="89cd9-136">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="89cd9-137">Spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="89cd9-137">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="89cd9-138">V každém z vašich souborů. csproj aktualizujte cílovou verzi rozhraní .NET Framework na `netcoreapp3.0` (nebo `netstandard2.1`, pokud se jedná o projekt knihovny).</span><span class="sxs-lookup"><span data-stu-id="89cd9-138">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="89cd9-139">To znamená upravit řádky formuláře:</span><span class="sxs-lookup"><span data-stu-id="89cd9-139">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    <span data-ttu-id="89cd9-140">Další podrobnosti o určení cílových rozhraní najdete [tady](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="89cd9-140">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="89cd9-141">Spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="89cd9-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    <span data-ttu-id="89cd9-142">Pokud váš projekt používá jiné balíčky Microsoft. prokládání (např. Microsoft. prohodně. Numerics), spusťte příkaz i pro tyto účely.</span><span class="sxs-lookup"><span data-stu-id="89cd9-142">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="89cd9-143">Uložte a zavřete všechny soubory.</span><span class="sxs-lookup"><span data-stu-id="89cd9-143">Save and close all files.</span></span>
6. <span data-ttu-id="89cd9-144">Opakujte 1-4 pro každou závislost projektu a pak přejděte zpátky do složky, která obsahuje váš hlavní projekt, a spusťte:</span><span class="sxs-lookup"><span data-stu-id="89cd9-144">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="89cd9-145">Když se teď aktualizují projekty Q #, aktualizujte QDK sám podle pokynů níže.</span><span class="sxs-lookup"><span data-stu-id="89cd9-145">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="89cd9-146">Aktualizace QDK</span><span class="sxs-lookup"><span data-stu-id="89cd9-146">Updating the QDK</span></span>

<span data-ttu-id="89cd9-147">Proces aktualizace QDK se liší v závislosti na vašem vývojovém jazyce a prostředí.</span><span class="sxs-lookup"><span data-stu-id="89cd9-147">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="89cd9-148">Níže vyberte vývojové prostředí.</span><span class="sxs-lookup"><span data-stu-id="89cd9-148">Select your development environment below.</span></span>

* [<span data-ttu-id="89cd9-149">Python: aktualizace rozšíření SWEETIQ #</span><span class="sxs-lookup"><span data-stu-id="89cd9-149">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="89cd9-150">Jupyter poznámkové bloky: aktualizace rozšíření SWEETIQ #</span><span class="sxs-lookup"><span data-stu-id="89cd9-150">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="89cd9-151">Visual Studio: aktualizace rozšíření QDK</span><span class="sxs-lookup"><span data-stu-id="89cd9-151">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="89cd9-152">VS Code: aktualizace rozšíření QDK</span><span class="sxs-lookup"><span data-stu-id="89cd9-152">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="89cd9-153">Příkazový řádek a C#: aktualizace šablon projektů</span><span class="sxs-lookup"><span data-stu-id="89cd9-153">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="89cd9-154">Aktualizace SWEETIQ # pro Python</span><span class="sxs-lookup"><span data-stu-id="89cd9-154">Update IQ# for Python</span></span>

1. <span data-ttu-id="89cd9-155">Aktualizace jádra `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="89cd9-155">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="89cd9-156">Ověření verze `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="89cd9-156">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="89cd9-157">Měl by se zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="89cd9-157">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="89cd9-158">Nedělejte si starosti, pokud je verze `iqsharp` vyšší, měla by odpovídat [nejnovější verzi](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="89cd9-158">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="89cd9-159">Aktualizace balíčku `qsharp`</span><span class="sxs-lookup"><span data-stu-id="89cd9-159">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="89cd9-160">Ověření verze `qsharp`</span><span class="sxs-lookup"><span data-stu-id="89cd9-160">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="89cd9-161">Měl by se zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="89cd9-161">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="89cd9-162">Z umístění souborů `.qs` spusťte následující příkaz</span><span class="sxs-lookup"><span data-stu-id="89cd9-162">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="89cd9-163">Teď můžete pomocí aktualizované verze QDK spouštět stávající programy pro užívání.</span><span class="sxs-lookup"><span data-stu-id="89cd9-163">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="89cd9-164">Aktualizace SWEETIQ # pro notebooky Jupyter</span><span class="sxs-lookup"><span data-stu-id="89cd9-164">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="89cd9-165">Aktualizace jádra `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="89cd9-165">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="89cd9-166">Ověření verze `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="89cd9-166">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="89cd9-167">Výstup by měl vypadat přibližně takto:</span><span class="sxs-lookup"><span data-stu-id="89cd9-167">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="89cd9-168">Nedělejte si starosti, pokud je verze `iqsharp` vyšší, měla by odpovídat [nejnovější verzi](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="89cd9-168">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="89cd9-169">Z buňky v Jupyter Notebook spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="89cd9-169">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="89cd9-170">Teď můžete otevřít existující Poznámkový blok Jupyter a spustit ho s aktualizovaným QDK.</span><span class="sxs-lookup"><span data-stu-id="89cd9-170">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="89cd9-171">Aktualizovat rozšíření sady Visual Studio QDK</span><span class="sxs-lookup"><span data-stu-id="89cd9-171">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="89cd9-172">Aktualizace rozšíření Q # Visual Studio</span><span class="sxs-lookup"><span data-stu-id="89cd9-172">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="89cd9-173">Visual Studio vás vyzve, abyste přijali aktualizace [rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) .</span><span class="sxs-lookup"><span data-stu-id="89cd9-173">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="89cd9-174">Přijmout aktualizaci</span><span class="sxs-lookup"><span data-stu-id="89cd9-174">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="89cd9-175">Šablony projektu jsou aktualizovány pomocí rozšíření.</span><span class="sxs-lookup"><span data-stu-id="89cd9-175">The project templates are updated with the extension.</span></span> <span data-ttu-id="89cd9-176">Aktualizované šablony se vztahují pouze na nově vytvořené projekty.</span><span class="sxs-lookup"><span data-stu-id="89cd9-176">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="89cd9-177">Kód pro existující projekty není aktualizován při aktualizaci rozšíření.</span><span class="sxs-lookup"><span data-stu-id="89cd9-177">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="89cd9-178">Aktualizovat rozšíření VS Code QDK</span><span class="sxs-lookup"><span data-stu-id="89cd9-178">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="89cd9-179">Aktualizace rozšíření VS Code pro všechna pole</span><span class="sxs-lookup"><span data-stu-id="89cd9-179">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="89cd9-180">Restartovat VS Code</span><span class="sxs-lookup"><span data-stu-id="89cd9-180">Restart VS Code</span></span>
    - <span data-ttu-id="89cd9-181">Přejít na kartu **rozšíření**</span><span class="sxs-lookup"><span data-stu-id="89cd9-181">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="89cd9-182">Vyberte **Microsoft Quantum Development Kit pro rozšíření Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="89cd9-182">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="89cd9-183">Načíst znovu rozšíření</span><span class="sxs-lookup"><span data-stu-id="89cd9-183">Reload the extension</span></span>

2. <span data-ttu-id="89cd9-184">Aktualizace šablon projektů pro každé z nich:</span><span class="sxs-lookup"><span data-stu-id="89cd9-184">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="89cd9-185">Přejděte do části **Zobrazit** -> **Paleta příkazů**.</span><span class="sxs-lookup"><span data-stu-id="89cd9-185">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="89cd9-186">Vyberte **Q #: Instalace šablon projektů**</span><span class="sxs-lookup"><span data-stu-id="89cd9-186">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="89cd9-187">Po několika sekundách byste měli obdržet místní nabídku potvrzující, že se šablony projektů úspěšně nainstalovaly.</span><span class="sxs-lookup"><span data-stu-id="89cd9-187">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="89cd9-188">C#pomocí nástroje `dotnet`ho příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="89cd9-188">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="89cd9-189">Aktualizace šablon projektů pro každý produkt pro .NET</span><span class="sxs-lookup"><span data-stu-id="89cd9-189">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="89cd9-190">Co dále?</span><span class="sxs-lookup"><span data-stu-id="89cd9-190">What's next?</span></span>

<span data-ttu-id="89cd9-191">Teď, když jste v upřednostňovaném prostředí aktualizovali sadu pro vývoj pro práci s více operačními systémy, můžete pokračovat v vývoji a spouštění programů pro práci s více poli.</span><span class="sxs-lookup"><span data-stu-id="89cd9-191">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="89cd9-192">Pokud jste ještě nezapsali program, můžete začít s [prvním programem pro práci](xref:microsoft.quantum.write-program)za sebou.</span><span class="sxs-lookup"><span data-stu-id="89cd9-192">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
