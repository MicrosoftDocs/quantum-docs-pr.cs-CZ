---
title: Informace o tom, jak aktualizovat Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463281"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="51bf3-102">Aktualizace Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="51bf3-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="51bf3-103">Přečtěte si, jak aktualizovat Microsoft Quantum Development Kit (QDK) na nejnovější verzi.</span><span class="sxs-lookup"><span data-stu-id="51bf3-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="51bf3-104">V tomto článku se předpokládá, že už máte nainstalované QDK.</span><span class="sxs-lookup"><span data-stu-id="51bf3-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="51bf3-105">Pokud instalujete poprvé, přečtěte si [příručku k instalaci](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="51bf3-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>


## <a name="updating-q-projects"></a><span data-ttu-id="51bf3-106">Aktualizují se projekty Q #.</span><span class="sxs-lookup"><span data-stu-id="51bf3-106">Updating Q# Projects</span></span> 

1. <span data-ttu-id="51bf3-107">Nejprve nainstalujte nejnovější verzi [.NET Core SDK 3,0](https://dotnet.microsoft.com/download) a spusťte na příkazovém řádku následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="51bf3-107">First, install the latest version of the [.NET Core SDK 3.0](https://dotnet.microsoft.com/download) and run the following command in the command prompt:</span></span>
```bash
dotnet --version
```
 <span data-ttu-id="51bf3-108">Ověřte, že výstup je 3.0.100 nebo vyšší, a postupujte podle pokynů níže v závislosti na nastavení.</span><span class="sxs-lookup"><span data-stu-id="51bf3-108">Verify the output is 3.0.100 or higher, then follow the instructions below depending on your setup.</span></span>

### <a name="in-visual-studio"></a><span data-ttu-id="51bf3-109">V nástroji Visual Studio</span><span class="sxs-lookup"><span data-stu-id="51bf3-109">In Visual Studio</span></span>
 
 1. <span data-ttu-id="51bf3-110">Aktualizace na nejnovější verzi sady Visual Studio 2019 najdete [tady](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) pokyny.</span><span class="sxs-lookup"><span data-stu-id="51bf3-110">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
 2. <span data-ttu-id="51bf3-111">Otevřete řešení v aplikaci Visual Studio</span><span class="sxs-lookup"><span data-stu-id="51bf3-111">Open your solution in Visual Studio</span></span>
 3. <span data-ttu-id="51bf3-112">V nabídce vyberte sestavení > Vyčistit řešení.</span><span class="sxs-lookup"><span data-stu-id="51bf3-112">From the menu, select Build > Clean Solution</span></span> 
 4. <span data-ttu-id="51bf3-113">[Aktualizujte cílové rozhraní](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) v každém z vašich souborů. csproj na netcoreapp 3.0 (nebo netstandard 2.1, pokud se jedná o projekt knihovny).</span><span class="sxs-lookup"><span data-stu-id="51bf3-113">[Update the target framework](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
 5. <span data-ttu-id="51bf3-114">Uložit a zavřít všechny soubory ve vašem řešení</span><span class="sxs-lookup"><span data-stu-id="51bf3-114">Save and close all files in your solution</span></span>
 6. <span data-ttu-id="51bf3-115">Vyberte nástroje > příkazového řádku > Developer Command Prompt</span><span class="sxs-lookup"><span data-stu-id="51bf3-115">Select Tools > Command Line > Developer Command Prompt</span></span>
 7. <span data-ttu-id="51bf3-116">Pro každý projekt v řešení spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="51bf3-116">For each project in the solution, run the following command:</span></span>
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
<span data-ttu-id="51bf3-117">Pokud vaše projekty používají jiné balíčky Microsoft., spusťte příkaz i pro tyto.</span><span class="sxs-lookup"><span data-stu-id="51bf3-117">If your projects use any other Microsoft.Quantum packages, run the command for these too.</span></span> 
 8. <span data-ttu-id="51bf3-118">Zavřete příkazový řádek a vyberte sestavení Build > Build ( *nevybírejte znovu* sestavit řešení, protože opětovné sestavení se zpočátku nezdaří)</span><span class="sxs-lookup"><span data-stu-id="51bf3-118">Close the command prompt and select Build > Build Solution (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

### <a name="in-visual-studio-code"></a><span data-ttu-id="51bf3-119">V Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="51bf3-119">In Visual Studio Code</span></span>

1. <span data-ttu-id="51bf3-120">V Visual Studio Code otevřete složku obsahující projekt, který chcete aktualizovat.</span><span class="sxs-lookup"><span data-stu-id="51bf3-120">In Visual Studio Code, open the folder containing the project to update</span></span>
1. <span data-ttu-id="51bf3-121">Výběr terminálu > nového terminálu</span><span class="sxs-lookup"><span data-stu-id="51bf3-121">Select Terminal > New Terminal</span></span>
1. <span data-ttu-id="51bf3-122">Postupujte podle pokynů pro aktualizaci pomocí příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="51bf3-122">Follow the instructions for updating using the command line</span></span>

### <a name="using-the-command-line"></a><span data-ttu-id="51bf3-123">Používání příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="51bf3-123">Using the command line</span></span>

1. <span data-ttu-id="51bf3-124">Přejděte do složky, která obsahuje soubor projektu.</span><span class="sxs-lookup"><span data-stu-id="51bf3-124">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="51bf3-125">Spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="51bf3-125">Run the following command:</span></span>
```bash
dotnet clean [project_name].csproj
```

3. <span data-ttu-id="51bf3-126">[Aktualizujte cílové rozhraní](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) v každém z vašich souborů. csproj na netcoreapp 3.0 (nebo netstandard 2.1, pokud se jedná o projekt knihovny).</span><span class="sxs-lookup"><span data-stu-id="51bf3-126">[Update the target framework](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
4. <span data-ttu-id="51bf3-127">Spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="51bf3-127">Run the following command:</span></span>
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
<span data-ttu-id="51bf3-128">Pokud váš projekt používá jiné balíčky Microsoft., spusťte příkaz pro tyto účely.</span><span class="sxs-lookup"><span data-stu-id="51bf3-128">if your project uses any other Microsoft.Quantum packages, run the command for these too.</span></span>

5. <span data-ttu-id="51bf3-129">Uložit a zavřít všechny soubory</span><span class="sxs-lookup"><span data-stu-id="51bf3-129">Save and close all files</span></span>
6. <span data-ttu-id="51bf3-130">Opakujte 1-4 pro každou závislost projektu a pak přejděte zpátky do složky, která obsahuje váš hlavní projekt, a spusťte:</span><span class="sxs-lookup"><span data-stu-id="51bf3-130">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a><span data-ttu-id="51bf3-131">Aktualizace SWEETIQ # pro Python</span><span class="sxs-lookup"><span data-stu-id="51bf3-131">Update IQ# for Python</span></span>

1. <span data-ttu-id="51bf3-132">Aktualizace jádra `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="51bf3-132">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="51bf3-133">Ověření verze `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="51bf3-133">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="51bf3-134">Měl by se zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="51bf3-134">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. <span data-ttu-id="51bf3-135">Aktualizace balíčku `qsharp`</span><span class="sxs-lookup"><span data-stu-id="51bf3-135">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="51bf3-136">Ověření verze `qsharp`</span><span class="sxs-lookup"><span data-stu-id="51bf3-136">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="51bf3-137">Měl by se zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="51bf3-137">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. <span data-ttu-id="51bf3-138">Z umístění souborů `.qs` spusťte následující příkaz</span><span class="sxs-lookup"><span data-stu-id="51bf3-138">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. <span data-ttu-id="51bf3-139">Teď můžete pomocí aktualizované verze QDK spouštět stávající programy pro užívání.</span><span class="sxs-lookup"><span data-stu-id="51bf3-139">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="51bf3-140">Aktualizace SWEETIQ # pro notebooky Jupyter</span><span class="sxs-lookup"><span data-stu-id="51bf3-140">Update IQ# for Jupyter notebooks</span></span>

1. <span data-ttu-id="51bf3-141">Aktualizace jádra `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="51bf3-141">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="51bf3-142">Ověření verze `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="51bf3-142">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="51bf3-143">Měl by se zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="51bf3-143">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. <span data-ttu-id="51bf3-144">Z buňky v Jupyter Notebook spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="51bf3-144">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

1. <span data-ttu-id="51bf3-145">Teď můžete otevřít existující Poznámkový blok Jupyter a spustit ho s aktualizovaným QDK.</span><span class="sxs-lookup"><span data-stu-id="51bf3-145">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="51bf3-146">Aktualizovat rozšíření sady Visual Studio QDK</span><span class="sxs-lookup"><span data-stu-id="51bf3-146">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="51bf3-147">Aktualizace rozšíření Q # Visual Studio</span><span class="sxs-lookup"><span data-stu-id="51bf3-147">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="51bf3-148">Visual Studio vás vyzve, abyste přijali aktualizace [rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) .</span><span class="sxs-lookup"><span data-stu-id="51bf3-148">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="51bf3-149">Přijmout aktualizaci</span><span class="sxs-lookup"><span data-stu-id="51bf3-149">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="51bf3-150">Šablony projektu jsou aktualizovány pomocí rozšíření.</span><span class="sxs-lookup"><span data-stu-id="51bf3-150">The project templates are updated with the extension.</span></span> <span data-ttu-id="51bf3-151">Aktualizované šablony se vztahují pouze na nově vytvořené projekty.</span><span class="sxs-lookup"><span data-stu-id="51bf3-151">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="51bf3-152">Kód pro existující projekty není aktualizován při aktualizaci rozšíření.</span><span class="sxs-lookup"><span data-stu-id="51bf3-152">The code for your existing projects is not updated when the extension is updated.</span></span>

## <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="51bf3-153">Aktualizovat rozšíření VS Code QDK</span><span class="sxs-lookup"><span data-stu-id="51bf3-153">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="51bf3-154">Aktualizace rozšíření VS Code pro všechna pole</span><span class="sxs-lookup"><span data-stu-id="51bf3-154">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="51bf3-155">Restartovat VS Code</span><span class="sxs-lookup"><span data-stu-id="51bf3-155">Restart VS Code</span></span>
    - <span data-ttu-id="51bf3-156">Přejít na kartu **rozšíření**</span><span class="sxs-lookup"><span data-stu-id="51bf3-156">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="51bf3-157">Vyberte **Microsoft Quantum Development Kit pro rozšíření Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="51bf3-157">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="51bf3-158">Načíst znovu rozšíření</span><span class="sxs-lookup"><span data-stu-id="51bf3-158">Reload the extension</span></span>

1. <span data-ttu-id="51bf3-159">Aktualizace šablon projektů pro každé z nich:</span><span class="sxs-lookup"><span data-stu-id="51bf3-159">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="51bf3-160">Přejít na **zobrazení** -> **paleta příkazů**</span><span class="sxs-lookup"><span data-stu-id="51bf3-160">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="51bf3-161">Vyberte **Q #: Instalace šablon projektů**</span><span class="sxs-lookup"><span data-stu-id="51bf3-161">Select **Q#: Install project templates**</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="51bf3-162">C#pomocí nástroje `dotnet`ho příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="51bf3-162">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="51bf3-163">Aktualizace šablon projektů pro každý produkt pro .NET</span><span class="sxs-lookup"><span data-stu-id="51bf3-163">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="51bf3-164">A co dál?</span><span class="sxs-lookup"><span data-stu-id="51bf3-164">What's next?</span></span>

<span data-ttu-id="51bf3-165">Teď, když jste v upřednostňovaném prostředí aktualizovali sadu pro vývoj pro práci s více operačními systémy, můžete pokračovat v vývoji a spouštění programů pro práci s více poli.</span><span class="sxs-lookup"><span data-stu-id="51bf3-165">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="51bf3-166">Pokud jste ještě nezapsali program, můžete začít s [prvním programem pro práci](xref:microsoft.quantum.write-program)za sebou.</span><span class="sxs-lookup"><span data-stu-id="51bf3-166">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
