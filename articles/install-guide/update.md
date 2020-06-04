---
title: Aktualizace sady pro vývoj pro QDK
description: 'V této části najdete popis postupu aktualizace projektů Q # a Microsoft Quantum Development Kit k aktuální verzi.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 3245f587493ce12cfec15c8f932fd092d85f688e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327560"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="c7258-103">Aktualizace Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="c7258-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="c7258-104">Přečtěte si, jak aktualizovat Microsoft Quantum Development Kit (QDK) na nejnovější verzi.</span><span class="sxs-lookup"><span data-stu-id="c7258-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="c7258-105">V tomto článku se předpokládá, že už máte nainstalované QDK.</span><span class="sxs-lookup"><span data-stu-id="c7258-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="c7258-106">Pokud instalujete poprvé, přečtěte si [příručku k instalaci](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="c7258-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="c7258-107">Doporučujeme, abyste si zachovali aktuálnost nejnovější verze QDK.</span><span class="sxs-lookup"><span data-stu-id="c7258-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="c7258-108">Postupujte podle tohoto průvodce aktualizací a upgradujte na nejnovější verzi QDK.</span><span class="sxs-lookup"><span data-stu-id="c7258-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="c7258-109">Proces se skládá ze dvou částí:</span><span class="sxs-lookup"><span data-stu-id="c7258-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="c7258-110">Aktualizace stávajících souborů a projektů Q # pro zarovnání kódu s aktualizovanou syntaxí.</span><span class="sxs-lookup"><span data-stu-id="c7258-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="c7258-111">Aktualizuje se QDK sám pro zvolené vývojové prostředí.</span><span class="sxs-lookup"><span data-stu-id="c7258-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="c7258-112">Aktualizují se projekty Q #.</span><span class="sxs-lookup"><span data-stu-id="c7258-112">Updating Q# Projects</span></span> 

<span data-ttu-id="c7258-113">Bez ohledu na to, jestli používáte C# nebo Python k hostování operací Q #, postupujte podle těchto pokynů a aktualizujte své projekty Q #.</span><span class="sxs-lookup"><span data-stu-id="c7258-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="c7258-114">Nejdřív ověřte, že máte nejnovější verzi [.NET Core SDK 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="c7258-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="c7258-115">Spusťte na příkazovém řádku následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="c7258-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="c7258-116">Ověřte, že výstup je `3.1.100` nebo vyšší.</span><span class="sxs-lookup"><span data-stu-id="c7258-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="c7258-117">Pokud ne, nainstalujte [nejnovější verzi](https://dotnet.microsoft.com/download) a zkuste to znovu.</span><span class="sxs-lookup"><span data-stu-id="c7258-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="c7258-118">Pak postupujte podle pokynů níže v závislosti na instalaci (Visual Studio, Visual Studio Code nebo přímo na příkazovém řádku).</span><span class="sxs-lookup"><span data-stu-id="c7258-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="c7258-119">Aktualizace projektů Q # v aplikaci Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c7258-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="c7258-120">Aktualizujte na nejnovější verzi sady Visual Studio 2019, pokyny najdete [tady](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) .</span><span class="sxs-lookup"><span data-stu-id="c7258-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="c7258-121">Otevřete řešení v aplikaci Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c7258-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="c7258-122">V nabídce vyberte **sestavit**  ->  **Vyčištění řešení**.</span><span class="sxs-lookup"><span data-stu-id="c7258-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="c7258-123">V každém z vašich souborů. csproj aktualizujte cílové rozhraní na `netcoreapp3.1` (nebo `netstandard2.1` Pokud se jedná o projekt knihovny).</span><span class="sxs-lookup"><span data-stu-id="c7258-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="c7258-124">To znamená upravit řádky formuláře:</span><span class="sxs-lookup"><span data-stu-id="c7258-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="c7258-125">Další podrobnosti o určení cílových rozhraní najdete [tady](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="c7258-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="c7258-126">V každém ze souborů. csproj nastavte sadu SDK na `Microsoft.Quantum.Sdk` , jak je uvedeno na řádku níže.</span><span class="sxs-lookup"><span data-stu-id="c7258-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="c7258-127">Všimněte si, že číslo verze by mělo být nejnovější dostupné a můžete ho zjistit pomocí [poznámky k verzi](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="c7258-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="c7258-128">Uložte a zavřete všechny soubory ve vašem řešení.</span><span class="sxs-lookup"><span data-stu-id="c7258-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="c7258-129">Vyberte **nástroje**  ->  **příkazového řádku**  ->  **Developer Command Prompt**.</span><span class="sxs-lookup"><span data-stu-id="c7258-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="c7258-130">Alternativně můžete použít konzolu pro správu balíčků v sadě Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c7258-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="c7258-131">Pro každý projekt v řešení spusťte následující příkaz pro **Odebrání** tohoto balíčku:</span><span class="sxs-lookup"><span data-stu-id="c7258-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="c7258-132">Pokud vaše projekty používají jakékoli jiné balíčky Microsoft. probíhat nebo Microsoft. Azure. (např. Microsoft. probíhat. NUMERIC), spusťte pro ně příkaz **Add** , který aktualizuje použitou verzi.</span><span class="sxs-lookup"><span data-stu-id="c7258-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="c7258-133">Zavřete příkazový řádek a vyberte **sestavení**  ->  **Build** Build (nevybírejte *not* znovu sestavit řešení).</span><span class="sxs-lookup"><span data-stu-id="c7258-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="c7258-134">Nyní můžete přeskočit k [aktualizaci rozšíření sady Visual Studio QDK](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="c7258-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="c7258-135">Aktualizace projektů Q # v Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c7258-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="c7258-136">V Visual Studio Code otevřete složku obsahující projekt, který chcete aktualizovat.</span><span class="sxs-lookup"><span data-stu-id="c7258-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="c7258-137">Vyberte **terminál**  ->  **Nový**terminál.</span><span class="sxs-lookup"><span data-stu-id="c7258-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="c7258-138">Postupujte podle pokynů pro aktualizaci pomocí příkazového řádku (přímo níže).</span><span class="sxs-lookup"><span data-stu-id="c7258-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="c7258-139">Aktualizace projektů Q # pomocí příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="c7258-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="c7258-140">Přejděte do složky, která obsahuje váš hlavní soubor projektu.</span><span class="sxs-lookup"><span data-stu-id="c7258-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="c7258-141">Spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="c7258-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="c7258-142">Určete aktuální verzi QDK.</span><span class="sxs-lookup"><span data-stu-id="c7258-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="c7258-143">Pokud ho chcete najít, můžete si přečíst [poznámky k verzi](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="c7258-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="c7258-144">Verze bude v podobném formátu `0.11.2006.207` .</span><span class="sxs-lookup"><span data-stu-id="c7258-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="c7258-145">V každém z vašich `.csproj` souborů Projděte následující kroky:</span><span class="sxs-lookup"><span data-stu-id="c7258-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="c7258-146">Aktualizujte cílové rozhraní na `netcoreapp3.1` (nebo `netstandard2.1` Pokud se jedná o projekt knihovny).</span><span class="sxs-lookup"><span data-stu-id="c7258-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="c7258-147">To znamená upravit řádky formuláře:</span><span class="sxs-lookup"><span data-stu-id="c7258-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="c7258-148">Další podrobnosti o určení cílových rozhraní najdete [tady](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="c7258-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="c7258-149">Nahraďte odkaz na sadu SDK v definici projektu.</span><span class="sxs-lookup"><span data-stu-id="c7258-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="c7258-150">Ujistěte se, že číslo verze odpovídá hodnotě určené v **kroku 3**.</span><span class="sxs-lookup"><span data-stu-id="c7258-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="c7258-151">Pokud je k dispozici, odeberte odkaz na balíček `Microsoft.Quantum.Development.Kit` , který bude zadán v následující položce:</span><span class="sxs-lookup"><span data-stu-id="c7258-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="c7258-152">Aktualizujte verzi všech balíčků pro neplatnost od Microsoftu na nejnovější vydanou verzi QDK (stanovenou v **kroku 3**).</span><span class="sxs-lookup"><span data-stu-id="c7258-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="c7258-153">Tyto balíčky jsou pojmenovány s následujícími vzory:</span><span class="sxs-lookup"><span data-stu-id="c7258-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="c7258-154">Odkazy na balíčky mají následující formát:</span><span class="sxs-lookup"><span data-stu-id="c7258-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="c7258-155">Aktualizovaný soubor uložte.</span><span class="sxs-lookup"><span data-stu-id="c7258-155">Save the updated file.</span></span>

    - <span data-ttu-id="c7258-156">Obnovte závislosti projektu následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="c7258-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="c7258-157">Přejděte zpět do složky obsahující váš hlavní projekt a spusťte příkaz:</span><span class="sxs-lookup"><span data-stu-id="c7258-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="c7258-158">Když se teď aktualizují projekty Q #, aktualizujte QDK sám podle pokynů níže.</span><span class="sxs-lookup"><span data-stu-id="c7258-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="c7258-159">Aktualizace QDK</span><span class="sxs-lookup"><span data-stu-id="c7258-159">Updating the QDK</span></span>

<span data-ttu-id="c7258-160">Proces aktualizace QDK se liší v závislosti na vašem vývojovém jazyce a prostředí.</span><span class="sxs-lookup"><span data-stu-id="c7258-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="c7258-161">Níže vyberte vývojové prostředí.</span><span class="sxs-lookup"><span data-stu-id="c7258-161">Select your development environment below.</span></span>

* [<span data-ttu-id="c7258-162">Python: aktualizace rozšíření SWEETIQ #</span><span class="sxs-lookup"><span data-stu-id="c7258-162">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="c7258-163">Jupyter poznámkové bloky: aktualizace rozšíření SWEETIQ #</span><span class="sxs-lookup"><span data-stu-id="c7258-163">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="c7258-164">Visual Studio: aktualizace rozšíření QDK</span><span class="sxs-lookup"><span data-stu-id="c7258-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="c7258-165">VS Code: aktualizace rozšíření QDK</span><span class="sxs-lookup"><span data-stu-id="c7258-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="c7258-166">Příkazový řádek a C#: aktualizace šablon projektů</span><span class="sxs-lookup"><span data-stu-id="c7258-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="c7258-167">Aktualizace SWEETIQ # pro Python</span><span class="sxs-lookup"><span data-stu-id="c7258-167">Update IQ# for Python</span></span>

1. <span data-ttu-id="c7258-168">Aktualizace `iqsharp` jádra</span><span class="sxs-lookup"><span data-stu-id="c7258-168">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="c7258-169">Ověření `iqsharp` verze</span><span class="sxs-lookup"><span data-stu-id="c7258-169">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="c7258-170">Měl by se zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="c7258-170">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="c7258-171">Nedělejte si starosti `iqsharp` , pokud je vaše verze vyšší, měla by odpovídat [nejnovější verzi](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="c7258-171">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="c7258-172">Aktualizace `qsharp` balíčku</span><span class="sxs-lookup"><span data-stu-id="c7258-172">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="c7258-173">Ověření `qsharp` verze</span><span class="sxs-lookup"><span data-stu-id="c7258-173">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="c7258-174">Měl by se zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="c7258-174">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="c7258-175">Z umístění vašich souborů spusťte následující příkaz. `.qs`</span><span class="sxs-lookup"><span data-stu-id="c7258-175">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="c7258-176">Teď můžete pomocí aktualizované verze QDK spouštět stávající programy pro užívání.</span><span class="sxs-lookup"><span data-stu-id="c7258-176">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="c7258-177">Aktualizace SWEETIQ # pro notebooky Jupyter</span><span class="sxs-lookup"><span data-stu-id="c7258-177">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="c7258-178">Aktualizace `iqsharp` jádra</span><span class="sxs-lookup"><span data-stu-id="c7258-178">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="c7258-179">Ověření `iqsharp` verze</span><span class="sxs-lookup"><span data-stu-id="c7258-179">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="c7258-180">Výstup by měl vypadat přibližně takto:</span><span class="sxs-lookup"><span data-stu-id="c7258-180">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="c7258-181">Nedělejte si starosti `iqsharp` , pokud je vaše verze vyšší, měla by odpovídat [nejnovější verzi](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="c7258-181">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="c7258-182">Z buňky v Jupyter Notebook spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="c7258-182">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="c7258-183">Teď můžete otevřít existující Poznámkový blok Jupyter a spustit ho s aktualizovaným QDK.</span><span class="sxs-lookup"><span data-stu-id="c7258-183">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="c7258-184">Aktualizovat rozšíření sady Visual Studio QDK</span><span class="sxs-lookup"><span data-stu-id="c7258-184">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="c7258-185">Aktualizace rozšíření Q # Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c7258-185">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="c7258-186">Visual Studio vás vyzve, abyste přijali aktualizace [rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) .</span><span class="sxs-lookup"><span data-stu-id="c7258-186">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="c7258-187">Přijmout aktualizaci</span><span class="sxs-lookup"><span data-stu-id="c7258-187">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="c7258-188">Šablony projektu jsou aktualizovány pomocí rozšíření.</span><span class="sxs-lookup"><span data-stu-id="c7258-188">The project templates are updated with the extension.</span></span> <span data-ttu-id="c7258-189">Aktualizované šablony se vztahují pouze na nově vytvořené projekty.</span><span class="sxs-lookup"><span data-stu-id="c7258-189">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="c7258-190">Kód pro existující projekty není aktualizován při aktualizaci rozšíření.</span><span class="sxs-lookup"><span data-stu-id="c7258-190">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="c7258-191">Aktualizovat rozšíření VS Code QDK</span><span class="sxs-lookup"><span data-stu-id="c7258-191">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="c7258-192">Aktualizace rozšíření VS Code pro všechna pole</span><span class="sxs-lookup"><span data-stu-id="c7258-192">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="c7258-193">Restartovat VS Code</span><span class="sxs-lookup"><span data-stu-id="c7258-193">Restart VS Code</span></span>
    - <span data-ttu-id="c7258-194">Přejít na kartu **rozšíření**</span><span class="sxs-lookup"><span data-stu-id="c7258-194">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="c7258-195">Vyberte **Microsoft Quantum Development Kit pro rozšíření Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="c7258-195">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="c7258-196">Načíst znovu rozšíření</span><span class="sxs-lookup"><span data-stu-id="c7258-196">Reload the extension</span></span>

2. <span data-ttu-id="c7258-197">Aktualizace šablon projektů pro každé z nich:</span><span class="sxs-lookup"><span data-stu-id="c7258-197">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="c7258-198">Přejít na **View**  ->  **paletu příkazů** zobrazení</span><span class="sxs-lookup"><span data-stu-id="c7258-198">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="c7258-199">Vyberte **Q #: Instalace šablon projektů**</span><span class="sxs-lookup"><span data-stu-id="c7258-199">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="c7258-200">Po několika sekundách byste měli obdržet místní nabídku potvrzující, že se šablony projektů úspěšně nainstalovaly.</span><span class="sxs-lookup"><span data-stu-id="c7258-200">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="c7258-201">C#, použití `dotnet` nástroje příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="c7258-201">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="c7258-202">Aktualizace šablon projektů pro každý produkt pro .NET</span><span class="sxs-lookup"><span data-stu-id="c7258-202">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
