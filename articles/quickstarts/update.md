---
title: Aktualizace sady Quantum Development Kit (QDK)
description: Tento článek popisuje aktualizaci projektů Q# a sady Microsoft Quantum Development Kit na aktuální verzi.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 8d39716c4d4c96ad87862b4b185895aab66cd210
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274044"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="80381-103">Aktualizace sady Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="80381-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="80381-104">Přečtěte si, jak aktualizovat sadu Microsoft Quantum Development Kit (QDK) na nejnovější verzi.</span><span class="sxs-lookup"><span data-stu-id="80381-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="80381-105">Tento článek předpokládá, že už máte sadu QDK nainstalovanou.</span><span class="sxs-lookup"><span data-stu-id="80381-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="80381-106">Pokud ji instalujete poprvé, přečtěte si informace v [průvodci instalací](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="80381-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="80381-107">Doporučujeme, abyste sadu QDK udržovali stále aktuální.</span><span class="sxs-lookup"><span data-stu-id="80381-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="80381-108">Podle tohoto průvodce upgradujte na nejnovější verzi sady QDK.</span><span class="sxs-lookup"><span data-stu-id="80381-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="80381-109">Proces se skládá ze dvou částí:</span><span class="sxs-lookup"><span data-stu-id="80381-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="80381-110">Aktualizace stávajících souborů a projektů Q# podle aktualizované syntaxe.</span><span class="sxs-lookup"><span data-stu-id="80381-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="80381-111">Aktualizace samotné sady QDK pro zvolené vývojové prostředí.</span><span class="sxs-lookup"><span data-stu-id="80381-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="80381-112">Aktualizace projektů Q#.</span><span class="sxs-lookup"><span data-stu-id="80381-112">Updating Q# Projects</span></span> 

<span data-ttu-id="80381-113">Své projekty Q# aktualizujte podle těchto pokynů bez ohledu na to, jestli k hostování operací Q# používáte jazyk C#, nebo Python.</span><span class="sxs-lookup"><span data-stu-id="80381-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="80381-114">Nejdřív ověřte, že máte nejnovější verzi [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="80381-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="80381-115">Na příkazovém řádku spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="80381-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="80381-116">Zkontrolujte, že výsledek je `3.1.100` nebo vyšší.</span><span class="sxs-lookup"><span data-stu-id="80381-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="80381-117">Pokud ne, nainstalujte [nejnovější verzi](https://dotnet.microsoft.com/download) a zkontrolujte ji znovu.</span><span class="sxs-lookup"><span data-stu-id="80381-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="80381-118">Pak postupujte podle pokynů níže v závislosti na vaší instalaci (Visual Studio, Visual Studio Code nebo přímo na příkazovém řádku).</span><span class="sxs-lookup"><span data-stu-id="80381-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="80381-119">Aktualizace projektů Q# v sadě Visual Studio</span><span class="sxs-lookup"><span data-stu-id="80381-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="80381-120">Aktualizujte na nejnovější verzi sady Visual Studio 2019, pokyny najdete [zde](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="80381-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="80381-121">Otevřete své řešení v prostředí Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="80381-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="80381-122">V nabídce vyberte **Kompilovat** -> **Vyčistit řešení**.</span><span class="sxs-lookup"><span data-stu-id="80381-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="80381-123">V každém z vašich souborů .csproj aktualizujte cílovou architekturu na `netcoreapp3.1` (nebo `netstandard2.1`, pokud se jedná o projekt knihovny).</span><span class="sxs-lookup"><span data-stu-id="80381-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="80381-124">To znamená upravit řádky formuláře:</span><span class="sxs-lookup"><span data-stu-id="80381-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="80381-125">Další podrobnosti o určení cílových architektur [najdete zde](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="80381-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="80381-126">V každém ze souborů. csproj nastavte sadu SDK na `Microsoft.Quantum.Sdk`, jak je uvedeno na řádku níže.</span><span class="sxs-lookup"><span data-stu-id="80381-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="80381-127">Všimněte si, že číslo verze by mělo být nejnovější dostupné a můžete ho zjistit z [poznámek k verzi](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="80381-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="80381-128">Uložte a zavřete všechny soubory ve vašem řešení.</span><span class="sxs-lookup"><span data-stu-id="80381-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="80381-129">Vyberte **Nástroje** -> **Příkazový řádek** -> **Developer Command Prompt**.</span><span class="sxs-lookup"><span data-stu-id="80381-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="80381-130">Můžete případně použít i konzolu pro správu balíčků v sadě Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="80381-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="80381-131">Pro každý projekt v řešení spusťte následující příkaz, který **odstraní** tento balíček:</span><span class="sxs-lookup"><span data-stu-id="80381-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="80381-132">Pokud vaše projekty používají jakékoli jiné balíčky Microsoft.Quantum nebo Microsoft.Azure.Quantum (např. Microsoft.Quantum.Numerics), příkazem **add** aktualizujte jejich použité verze.</span><span class="sxs-lookup"><span data-stu-id="80381-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="80381-133">Zavřete příkazový řádek a zvolte **Kompilovat** -> **Kompilovat řešení** (*nevybírejte* Znovu zkompilovat řešení).</span><span class="sxs-lookup"><span data-stu-id="80381-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="80381-134">Nyní můžete přeskočit na [aktualizaci rozšíření sady Visual Studio QDK](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="80381-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="80381-135">Aktualizace projektů Q# v sadě Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="80381-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="80381-136">V sadě Visual Studio Code otevřete složku obsahující projekt, který chcete aktualizovat.</span><span class="sxs-lookup"><span data-stu-id="80381-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="80381-137">Vyberte **Terminál** -> **Nový Terminál**.</span><span class="sxs-lookup"><span data-stu-id="80381-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="80381-138">Postupujte podle následujících pokynů pro aktualizaci pomocí příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="80381-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="80381-139">Aktualizace projektů Q# pomocí příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="80381-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="80381-140">Přejděte do složky, která obsahuje váš hlavní soubor projektu.</span><span class="sxs-lookup"><span data-stu-id="80381-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="80381-141">Spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="80381-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="80381-142">Určete aktuální verzi sady QDK.</span><span class="sxs-lookup"><span data-stu-id="80381-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="80381-143">Zjistíte ho třeba v [poznámkách k verzi](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="80381-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="80381-144">Verze bude mít tvar `0.11.2006.207`.</span><span class="sxs-lookup"><span data-stu-id="80381-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="80381-145">V každém ze souborů `.csproj` proveďte následující postup:</span><span class="sxs-lookup"><span data-stu-id="80381-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="80381-146">Aktualizujte cílovou architekturu na `netcoreapp3.1` (nebo `netstandard2.1`, pokud se jedná o projekt knihovny).</span><span class="sxs-lookup"><span data-stu-id="80381-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="80381-147">To znamená upravit řádky formuláře:</span><span class="sxs-lookup"><span data-stu-id="80381-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="80381-148">Další podrobnosti o určení cílových architektur [najdete zde](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="80381-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="80381-149">Nahraďte odkaz na sadu SDK v definici projektu.</span><span class="sxs-lookup"><span data-stu-id="80381-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="80381-150">Ujistěte se, že číslo verze odpovídá hodnotě zjištěné v **kroku 3**.</span><span class="sxs-lookup"><span data-stu-id="80381-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="80381-151">Pokud existuje, odeberte odkaz na balíček `Microsoft.Quantum.Development.Kit`, který bude zadán v následující položce:</span><span class="sxs-lookup"><span data-stu-id="80381-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="80381-152">Aktualizujte verzi všech balíčků Microsoft Quantum na nejnovější vydanou verzi QDK (zjištěnou v **kroku 3**).</span><span class="sxs-lookup"><span data-stu-id="80381-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="80381-153">Tyto balíčky mají názvy v následujícím tvaru:</span><span class="sxs-lookup"><span data-stu-id="80381-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="80381-154">Odkazy na balíčky mají následující tvar:</span><span class="sxs-lookup"><span data-stu-id="80381-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="80381-155">Aktualizovaný soubor uložte.</span><span class="sxs-lookup"><span data-stu-id="80381-155">Save the updated file.</span></span>

    - <span data-ttu-id="80381-156">Obnovte závislosti projektu následujícím postupem:</span><span class="sxs-lookup"><span data-stu-id="80381-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="80381-157">Přejděte zpět do složky, která obsahuje váš hlavní projekt, a spusťte příkaz:</span><span class="sxs-lookup"><span data-stu-id="80381-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="80381-158">Když teď máte aktualizované projekty Q#, podle následujících pokynů aktualizujte samotnou sadu QDK.</span><span class="sxs-lookup"><span data-stu-id="80381-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="80381-159">Aktualizace sady QDK</span><span class="sxs-lookup"><span data-stu-id="80381-159">Updating the QDK</span></span>

<span data-ttu-id="80381-160">Proces aktualizace sady QDK se liší v závislosti na vašem vývojovém jazyce a prostředí.</span><span class="sxs-lookup"><span data-stu-id="80381-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="80381-161">Vyberte své vývojové prostředí níže.</span><span class="sxs-lookup"><span data-stu-id="80381-161">Select your development environment below.</span></span>

* [<span data-ttu-id="80381-162">Python: aktualizace rozšíření IQ#</span><span class="sxs-lookup"><span data-stu-id="80381-162">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="80381-163">Jupyter Notebooks: aktualizace rozšíření IQ#</span><span class="sxs-lookup"><span data-stu-id="80381-163">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="80381-164">Visual Studio: aktualizace rozšíření QDK</span><span class="sxs-lookup"><span data-stu-id="80381-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="80381-165">VS Code: aktualizace rozšíření QDK</span><span class="sxs-lookup"><span data-stu-id="80381-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="80381-166">Příkazový řádek a C#: aktualizace šablon projektů</span><span class="sxs-lookup"><span data-stu-id="80381-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="80381-167">Aktualizace IQ# pro Python</span><span class="sxs-lookup"><span data-stu-id="80381-167">Update IQ# for Python</span></span>

1. <span data-ttu-id="80381-168">Aktualizujte jádro `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="80381-168">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="80381-169">Ověřte verzi `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="80381-169">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="80381-170">Měl by se zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="80381-170">You should see the following output:</span></span>

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="80381-171">Nedělejte si starosti, pokud je verze `iqsharp` vyšší, měla by odpovídat [nejnovějšímu vydání](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="80381-171">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="80381-172">Aktualizujte balíček `qsharp`</span><span class="sxs-lookup"><span data-stu-id="80381-172">Update the `qsharp` package</span></span>

    ```
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="80381-173">Ověřte verzi `qsharp`</span><span class="sxs-lookup"><span data-stu-id="80381-173">Verify the `qsharp` version</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="80381-174">Měl by se zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="80381-174">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="80381-175">Ve složce, kde jsou umístěné soubory `.qs`, spusťte následující příkaz</span><span class="sxs-lookup"><span data-stu-id="80381-175">Run the following command from the location of your `.qs` files</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="80381-176">Teď můžete pomocí aktualizované verze QDK zkusit spustit své kvantové programy.</span><span class="sxs-lookup"><span data-stu-id="80381-176">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="80381-177">Aktualizace IQ# pro Jupyter Notebooks</span><span class="sxs-lookup"><span data-stu-id="80381-177">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="80381-178">Aktualizujte jádro `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="80381-178">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="80381-179">Ověřte verzi `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="80381-179">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="80381-180">Výstup by měl vypadat přibližně takto:</span><span class="sxs-lookup"><span data-stu-id="80381-180">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="80381-181">Nedělejte si starosti, pokud je verze `iqsharp` vyšší, měla by odpovídat [nejnovějšímu vydání](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="80381-181">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="80381-182">Z buňky v poznámkovém bloku Jupyter spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="80381-182">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="80381-183">Teď můžete otevřít existující Poznámkový blok Jupyter a spustit ho s aktualizovanou sadou QDK.</span><span class="sxs-lookup"><span data-stu-id="80381-183">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="80381-184">Aktualizace rozšíření QDK sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="80381-184">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="80381-185">Aktualizujte rozšíření Q# sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="80381-185">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="80381-186">Visual Studio vás vyzve, abyste přijali aktualizace [rozšíření Quantum sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="80381-186">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="80381-187">Přijměte aktualizaci.</span><span class="sxs-lookup"><span data-stu-id="80381-187">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="80381-188">Šablony projektu budou aktualizovány spolu s rozšířením.</span><span class="sxs-lookup"><span data-stu-id="80381-188">The project templates are updated with the extension.</span></span> <span data-ttu-id="80381-189">Aktualizované šablony se uplatní jen na nově vytvořené projekty.</span><span class="sxs-lookup"><span data-stu-id="80381-189">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="80381-190">Kód stávajících projektů se při aktualizaci rozšíření nezmění.</span><span class="sxs-lookup"><span data-stu-id="80381-190">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="80381-191">Aktualizace rozšíření QDK sady VS Code</span><span class="sxs-lookup"><span data-stu-id="80381-191">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="80381-192">Aktualizujte rozšíření QDK sady VS Code</span><span class="sxs-lookup"><span data-stu-id="80381-192">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="80381-193">Restartujte VS Code</span><span class="sxs-lookup"><span data-stu-id="80381-193">Restart VS Code</span></span>
    - <span data-ttu-id="80381-194">Přejděte na kartu **Rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="80381-194">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="80381-195">Vyberte rozšíření **Microsoft Quantum Development Kit pro Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="80381-195">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="80381-196">Znovu načtěte rozšíření.</span><span class="sxs-lookup"><span data-stu-id="80381-196">Reload the extension</span></span>

2. <span data-ttu-id="80381-197">Aktualizujte šablony projektu Quantum:</span><span class="sxs-lookup"><span data-stu-id="80381-197">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="80381-198">Přejděte do části **Zobrazit** -> **Paleta příkazů**.</span><span class="sxs-lookup"><span data-stu-id="80381-198">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="80381-199">Vyberte **Q#: Nainstalovat šablony projektu**.</span><span class="sxs-lookup"><span data-stu-id="80381-199">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="80381-200">Po několika sekundách byste měli vidět okno potvrzující, že se šablony projektů úspěšně nainstalovaly.</span><span class="sxs-lookup"><span data-stu-id="80381-200">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="80381-201">C# s použitím nástroje příkazového řádku `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="80381-201">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="80381-202">Aktualizujte šablony projektu Quantum pro rozhraní .NET.</span><span class="sxs-lookup"><span data-stu-id="80381-202">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
