---
title: Aktualizace sady Quantum Development Kit (QDK)
description: Tento článek popisuje aktualizaci projektů v Q# a sady Microsoft Quantum Development Kit na aktuální verzi.
author: bradben
ms.author: v-benbra
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
no-loc:
- Q#
- $$v
ms.openlocfilehash: d9678a61f5fe4ca466b6a84e9e4b68321c5baee3
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834916"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="7abfb-103">Aktualizace sady Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="7abfb-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="7abfb-104">Přečtěte si, jak aktualizovat sadu Microsoft Quantum Development Kit (QDK) na nejnovější verzi.</span><span class="sxs-lookup"><span data-stu-id="7abfb-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="7abfb-105">Tento článek předpokládá, že už máte sadu QDK nainstalovanou.</span><span class="sxs-lookup"><span data-stu-id="7abfb-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="7abfb-106">Pokud ji instalujete poprvé, přečtěte si informace v [průvodci instalací](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="7abfb-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="7abfb-107">Doporučujeme, abyste sadu QDK udržovali stále aktuální.</span><span class="sxs-lookup"><span data-stu-id="7abfb-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="7abfb-108">Podle tohoto průvodce upgradujte na nejnovější verzi sady QDK.</span><span class="sxs-lookup"><span data-stu-id="7abfb-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="7abfb-109">Proces se skládá ze dvou částí:</span><span class="sxs-lookup"><span data-stu-id="7abfb-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="7abfb-110">Aktualizace stávajících souborů a projektů v Q# podle aktualizované syntaxe.</span><span class="sxs-lookup"><span data-stu-id="7abfb-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="7abfb-111">Aktualizace samotné sady QDK pro zvolené vývojové prostředí.</span><span class="sxs-lookup"><span data-stu-id="7abfb-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-no-locq-projects"></a><span data-ttu-id="7abfb-112">Aktualizace projektů v Q#</span><span class="sxs-lookup"><span data-stu-id="7abfb-112">Updating Q# Projects</span></span> 

<span data-ttu-id="7abfb-113">Své projekty v Q# aktualizujte podle těchto pokynů bez ohledu na to, jestli k hostování operací Q# používáte jazyk C#, nebo Python.</span><span class="sxs-lookup"><span data-stu-id="7abfb-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="7abfb-114">Nejdřív ověřte, že máte nejnovější verzi [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="7abfb-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="7abfb-115">Na příkazovém řádku spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="7abfb-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="7abfb-116">Zkontrolujte, že výsledek je `3.1.100` nebo vyšší.</span><span class="sxs-lookup"><span data-stu-id="7abfb-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="7abfb-117">Pokud ne, nainstalujte [nejnovější verzi](https://dotnet.microsoft.com/download) a zkontrolujte ji znovu.</span><span class="sxs-lookup"><span data-stu-id="7abfb-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="7abfb-118">Pak postupujte podle pokynů níže v závislosti na vaší instalaci (Visual Studio, Visual Studio Code nebo přímo z příkazového řádku).</span><span class="sxs-lookup"><span data-stu-id="7abfb-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly from the command prompt).</span></span>

### <a name="update-no-locq-projects-in-visual-studio"></a><span data-ttu-id="7abfb-119">Aktualizace projektů v Q# v sadě Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7abfb-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="7abfb-120">Aktualizujte na nejnovější verzi sady Visual Studio 2019, pokyny najdete [zde](https://docs.microsoft.com/visualstudio/install/update-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="7abfb-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio) for instructions.</span></span>
2. <span data-ttu-id="7abfb-121">Otevřete své řešení v prostředí Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7abfb-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="7abfb-122">V nabídce vyberte **Kompilovat** -> **Vyčistit řešení**.</span><span class="sxs-lookup"><span data-stu-id="7abfb-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="7abfb-123">V každém z vašich souborů .csproj aktualizujte cílovou architekturu na `netcoreapp3.1` (nebo `netstandard2.1`, pokud se jedná o projekt knihovny).</span><span class="sxs-lookup"><span data-stu-id="7abfb-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="7abfb-124">To znamená upravit řádky formuláře:</span><span class="sxs-lookup"><span data-stu-id="7abfb-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="7abfb-125">Další podrobnosti o určení cílových architektur [najdete zde](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="7abfb-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="7abfb-126">V každém ze souborů. csproj nastavte sadu SDK na `Microsoft.Quantum.Sdk`, jak je uvedeno na řádku níže.</span><span class="sxs-lookup"><span data-stu-id="7abfb-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="7abfb-127">Všimněte si, že číslo verze by mělo být nejnovější dostupné a můžete ho zjistit z [poznámek k verzi](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="7abfb-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    ```

6. <span data-ttu-id="7abfb-128">Uložte a zavřete všechny soubory ve vašem řešení.</span><span class="sxs-lookup"><span data-stu-id="7abfb-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="7abfb-129">Vyberte **Nástroje** -> **Příkazový řádek** -> **Developer Command Prompt**.</span><span class="sxs-lookup"><span data-stu-id="7abfb-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="7abfb-130">Můžete případně použít i konzolu pro správu balíčků v sadě Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7abfb-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="7abfb-131">Pro každý projekt v řešení spusťte následující příkaz, který **odstraní** tento balíček:</span><span class="sxs-lookup"><span data-stu-id="7abfb-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="7abfb-132">Pokud vaše projekty používají jakékoli jiné balíčky Microsoft.Quantum nebo Microsoft.Azure.Quantum (např. Microsoft.Quantum.Numerics), příkazem **add** aktualizujte jejich použité verze.</span><span class="sxs-lookup"><span data-stu-id="7abfb-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="7abfb-133">Zavřete příkazový řádek a zvolte **Kompilovat** -> **Kompilovat řešení** (*nevybírejte* Znovu zkompilovat řešení).</span><span class="sxs-lookup"><span data-stu-id="7abfb-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="7abfb-134">Nyní můžete přeskočit na [aktualizaci rozšíření sady Visual Studio QDK](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="7abfb-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-no-locq-projects-in-visual-studio-code"></a><span data-ttu-id="7abfb-135">Aktualizace projektů v Q# v editoru Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="7abfb-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="7abfb-136">V sadě Visual Studio Code otevřete složku obsahující projekt, který chcete aktualizovat.</span><span class="sxs-lookup"><span data-stu-id="7abfb-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="7abfb-137">Vyberte **Terminál** -> **Nový Terminál**.</span><span class="sxs-lookup"><span data-stu-id="7abfb-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="7abfb-138">Postupujte podle následujících pokynů pro aktualizaci pomocí příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="7abfb-138">Follow the instructions for updating using the command prompt (directly below).</span></span>

### <a name="update-no-locq-projects-using-the-command-prompt"></a><span data-ttu-id="7abfb-139">Aktualizace projektů v Q# pomocí příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="7abfb-139">Update Q# projects using the command prompt</span></span>

1. <span data-ttu-id="7abfb-140">Přejděte do složky, která obsahuje váš hlavní soubor projektu.</span><span class="sxs-lookup"><span data-stu-id="7abfb-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="7abfb-141">Spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="7abfb-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="7abfb-142">Určete aktuální verzi sady QDK.</span><span class="sxs-lookup"><span data-stu-id="7abfb-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="7abfb-143">Zjistíte ho třeba v [poznámkách k verzi](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="7abfb-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="7abfb-144">Verze bude mít tvar `0.12.20072031`.</span><span class="sxs-lookup"><span data-stu-id="7abfb-144">The version will be in a format similar to `0.12.20072031`.</span></span>

4. <span data-ttu-id="7abfb-145">V každém ze souborů `.csproj` proveďte následující postup:</span><span class="sxs-lookup"><span data-stu-id="7abfb-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="7abfb-146">Aktualizujte cílovou architekturu na `netcoreapp3.1` (nebo `netstandard2.1`, pokud se jedná o projekt knihovny).</span><span class="sxs-lookup"><span data-stu-id="7abfb-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="7abfb-147">To znamená upravit řádky formuláře:</span><span class="sxs-lookup"><span data-stu-id="7abfb-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="7abfb-148">Další podrobnosti o určení cílových architektur [najdete zde](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="7abfb-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="7abfb-149">Nahraďte odkaz na sadu SDK v definici projektu.</span><span class="sxs-lookup"><span data-stu-id="7abfb-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="7abfb-150">Ujistěte se, že číslo verze odpovídá hodnotě zjištěné v **kroku 3**.</span><span class="sxs-lookup"><span data-stu-id="7abfb-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
        ```

    - <span data-ttu-id="7abfb-151">Pokud existuje, odeberte odkaz na balíček `Microsoft.Quantum.Development.Kit`, který bude zadán v následující položce:</span><span class="sxs-lookup"><span data-stu-id="7abfb-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="7abfb-152">Aktualizujte verzi všech balíčků Microsoft Quantum na nejnovější vydanou verzi QDK (zjištěnou v **kroku 3**).</span><span class="sxs-lookup"><span data-stu-id="7abfb-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="7abfb-153">Tyto balíčky mají názvy v následujícím tvaru:</span><span class="sxs-lookup"><span data-stu-id="7abfb-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="7abfb-154">Odkazy na balíčky mají následující tvar:</span><span class="sxs-lookup"><span data-stu-id="7abfb-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
        ```

    - <span data-ttu-id="7abfb-155">Aktualizovaný soubor uložte.</span><span class="sxs-lookup"><span data-stu-id="7abfb-155">Save the updated file.</span></span>

    - <span data-ttu-id="7abfb-156">Obnovte závislosti projektu následujícím postupem:</span><span class="sxs-lookup"><span data-stu-id="7abfb-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="7abfb-157">Přejděte zpět do složky, která obsahuje váš hlavní projekt, a spusťte příkaz:</span><span class="sxs-lookup"><span data-stu-id="7abfb-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="7abfb-158">Když teď máte projekty v Q# aktualizované, podle následujících pokynů aktualizujte samotnou sadu QDK.</span><span class="sxs-lookup"><span data-stu-id="7abfb-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="7abfb-159">Aktualizace sady QDK</span><span class="sxs-lookup"><span data-stu-id="7abfb-159">Updating the QDK</span></span>

<span data-ttu-id="7abfb-160">Proces aktualizace sady QDK se liší v závislosti na vašem vývojovém jazyce a prostředí.</span><span class="sxs-lookup"><span data-stu-id="7abfb-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="7abfb-161">Vyberte své vývojové prostředí níže.</span><span class="sxs-lookup"><span data-stu-id="7abfb-161">Select your development environment below.</span></span>

* [<span data-ttu-id="7abfb-162">Python: aktualizace balíčku `qsharp`</span><span class="sxs-lookup"><span data-stu-id="7abfb-162">Python: update the `qsharp` package</span></span>](#update-the-qsharp-python-package)
* [<span data-ttu-id="7abfb-163">Aplikace Jupyter Notebook: aktualizace jádra IQ#</span><span class="sxs-lookup"><span data-stu-id="7abfb-163">Jupyter Notebooks: update the IQ# kernel</span></span>](#update-the-iq-jupyter-kernel)
* [<span data-ttu-id="7abfb-164">Visual Studio: aktualizace rozšíření QDK</span><span class="sxs-lookup"><span data-stu-id="7abfb-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="7abfb-165">VS Code: aktualizace rozšíření QDK</span><span class="sxs-lookup"><span data-stu-id="7abfb-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="7abfb-166">Příkazový řádek a C#: aktualizace šablon projektů</span><span class="sxs-lookup"><span data-stu-id="7abfb-166">Command line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a><span data-ttu-id="7abfb-167">Aktualizace balíčku Pythonu `qsharp`</span><span class="sxs-lookup"><span data-stu-id="7abfb-167">Update the `qsharp` Python package</span></span>

<span data-ttu-id="7abfb-168">Postup aktualizace závisí na tom, jestli jste původně provedli instalaci pomocí prostředí conda, nebo pomocí rozhraní .NET CLI a pip.</span><span class="sxs-lookup"><span data-stu-id="7abfb-168">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="7abfb-169">Aktualizace pomocí prostředí conda (doporučeno)</span><span class="sxs-lookup"><span data-stu-id="7abfb-169">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="7abfb-170">Aktivujte prostředí conda, do kterého jste nainstalovali balíček `qsharp`, a potom proveďte aktualizaci spuštěním tohoto příkazu:</span><span class="sxs-lookup"><span data-stu-id="7abfb-170">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="7abfb-171">Ve složce, kde jsou umístěné soubory `.qs`, spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="7abfb-171">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="7abfb-172">Aktualizace pomocí rozhraní .NET CLI a pip (rozšířené)</span><span class="sxs-lookup"><span data-stu-id="7abfb-172">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="7abfb-173">Aktualizujte jádro `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="7abfb-173">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="7abfb-174">Ověřte verzi `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="7abfb-174">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="7abfb-175">Měl by se zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="7abfb-175">You should see the following output:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="7abfb-176">Nedělejte si starosti, pokud je vaše verze `iqsharp` vyšší.</span><span class="sxs-lookup"><span data-stu-id="7abfb-176">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="7abfb-177">Měla by odpovídat [nejnovější verzi](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="7abfb-177">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="7abfb-178">Aktualizujte balíček `qsharp`:</span><span class="sxs-lookup"><span data-stu-id="7abfb-178">Update the `qsharp` package:</span></span>

    ```
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="7abfb-179">Ověřte verzi `qsharp`:</span><span class="sxs-lookup"><span data-stu-id="7abfb-179">Verify the `qsharp` version:</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="7abfb-180">Měl by se zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="7abfb-180">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="7abfb-181">Ve složce, kde jsou umístěné soubory `.qs`, spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="7abfb-181">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

<span data-ttu-id="7abfb-182">Teď můžete pomocí aktualizovaného balíčku Pythonu `qsharp` zkusit spustit své kvantové programy.</span><span class="sxs-lookup"><span data-stu-id="7abfb-182">You can now use the updated `qsharp` Python package to run your existing quantum programs.</span></span>

### <a name="update-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="7abfb-183">Aktualizace jádra IQ# Jupyter</span><span class="sxs-lookup"><span data-stu-id="7abfb-183">Update the IQ# Jupyter kernel</span></span>

<span data-ttu-id="7abfb-184">Postup aktualizace závisí na tom, jestli jste původně provedli instalaci pomocí prostředí conda, nebo pomocí rozhraní .NET CLI a pip.</span><span class="sxs-lookup"><span data-stu-id="7abfb-184">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="7abfb-185">Aktualizace pomocí prostředí conda (doporučeno)</span><span class="sxs-lookup"><span data-stu-id="7abfb-185">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="7abfb-186">Aktivujte prostředí conda, do kterého jste nainstalovali balíček `qsharp`, a potom proveďte aktualizaci spuštěním tohoto příkazu:</span><span class="sxs-lookup"><span data-stu-id="7abfb-186">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="7abfb-187">Z buňky v každé aplikaci Jupyter Notebook s podporou Q# spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="7abfb-187">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="7abfb-188">Aktualizace pomocí rozhraní .NET CLI a pip (rozšířené)</span><span class="sxs-lookup"><span data-stu-id="7abfb-188">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="7abfb-189">Aktualizujte balíček `Microsoft.Quantum.IQSharp`:</span><span class="sxs-lookup"><span data-stu-id="7abfb-189">Update the `Microsoft.Quantum.IQSharp` package:</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="7abfb-190">Ověřte verzi `iqsharp`:</span><span class="sxs-lookup"><span data-stu-id="7abfb-190">Verify the `iqsharp` version:</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="7abfb-191">Výstup by měl vypadat přibližně takto:</span><span class="sxs-lookup"><span data-stu-id="7abfb-191">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="7abfb-192">Nedělejte si starosti, pokud je vaše verze `iqsharp` vyšší.</span><span class="sxs-lookup"><span data-stu-id="7abfb-192">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="7abfb-193">Měla by odpovídat [nejnovější verzi](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="7abfb-193">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="7abfb-194">Z buňky v každé aplikaci Jupyter Notebook s podporou Q# spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="7abfb-194">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

***

<span data-ttu-id="7abfb-195">Teď můžete pomocí aktualizovaného jádra IQ# spustit stávající služby Jupyter Notebook s podporou Q#.</span><span class="sxs-lookup"><span data-stu-id="7abfb-195">You can now use the updated IQ# kernel to run your existing Q# Jupyter Notebooks.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="7abfb-196">Aktualizace rozšíření QDK sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7abfb-196">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="7abfb-197">Aktualizujte rozšíření Q# sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7abfb-197">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="7abfb-198">Visual Studio vás vyzve, abyste přijali aktualizace [rozšíření Quantum sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="7abfb-198">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="7abfb-199">Přijměte aktualizaci.</span><span class="sxs-lookup"><span data-stu-id="7abfb-199">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="7abfb-200">Šablony projektu budou aktualizovány spolu s rozšířením.</span><span class="sxs-lookup"><span data-stu-id="7abfb-200">The project templates are updated with the extension.</span></span> <span data-ttu-id="7abfb-201">Aktualizované šablony se uplatní jen na nově vytvořené projekty.</span><span class="sxs-lookup"><span data-stu-id="7abfb-201">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="7abfb-202">Kód stávajících projektů se při aktualizaci rozšíření nezmění.</span><span class="sxs-lookup"><span data-stu-id="7abfb-202">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="7abfb-203">Aktualizace rozšíření QDK sady VS Code</span><span class="sxs-lookup"><span data-stu-id="7abfb-203">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="7abfb-204">Aktualizujte rozšíření QDK sady VS Code</span><span class="sxs-lookup"><span data-stu-id="7abfb-204">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="7abfb-205">Restartujte VS Code</span><span class="sxs-lookup"><span data-stu-id="7abfb-205">Restart VS Code</span></span>
    - <span data-ttu-id="7abfb-206">Přejděte na kartu **Rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="7abfb-206">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="7abfb-207">Vyberte rozšíření **Microsoft Quantum Development Kit pro Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="7abfb-207">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="7abfb-208">Znovu načtěte rozšíření.</span><span class="sxs-lookup"><span data-stu-id="7abfb-208">Reload the extension</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="7abfb-209">C# s použitím nástroje příkazového řádku `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="7abfb-209">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="7abfb-210">Aktualizujte šablony projektu Quantum pro rozhraní .NET.</span><span class="sxs-lookup"><span data-stu-id="7abfb-210">Update the Quantum project templates for .NET</span></span>

    <span data-ttu-id="7abfb-211">Na příkazovém řádku zadejte:</span><span class="sxs-lookup"><span data-stu-id="7abfb-211">From the command prompt:</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   <span data-ttu-id="7abfb-212">Případně pokud máte v úmyslu používat šablony příkazového řádku a už máte nainstalované rozšíření VS Code QDK, můžete aktualizovat šablony projektu ze samotného rozšíření:</span><span class="sxs-lookup"><span data-stu-id="7abfb-212">Alternatively, if you intend to use the command-line templates, and already have the VS Code QDK extension installed, you can update the project templates from the extension itself:</span></span>

   - [<span data-ttu-id="7abfb-213">Aktualizace rozšíření QDK</span><span class="sxs-lookup"><span data-stu-id="7abfb-213">Update the QDK extension</span></span>](#update-vs-code-qdk-extension)
   - <span data-ttu-id="7abfb-214">V editoru VS Code přejděte do části **Zobrazit** -> **Paleta příkazů**.</span><span class="sxs-lookup"><span data-stu-id="7abfb-214">In VS Code, go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="7abfb-215">Vyberte **Q#: Instalace šablon projektů pro příkazový řádek**.</span><span class="sxs-lookup"><span data-stu-id="7abfb-215">Select **Q#: Install command line project templates**</span></span>
   - <span data-ttu-id="7abfb-216">Po několika sekundách byste měli vidět okno potvrzující, že se šablony projektů úspěšně nainstalovaly.</span><span class="sxs-lookup"><span data-stu-id="7abfb-216">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>
