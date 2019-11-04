---
title: Informace o tom, jak aktualizovat Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185847"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="2a4d7-102">Aktualizace Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="2a4d7-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="2a4d7-103">Přečtěte si, jak aktualizovat Microsoft Quantum Development Kit (QDK) na nejnovější verzi.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="2a4d7-104">V tomto článku se předpokládá, že už máte nainstalované QDK.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="2a4d7-105">Pokud instalujete poprvé, přečtěte si [příručku k instalaci](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="2a4d7-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="2a4d7-106">Postup aktualizace závisí na vašem vývojovém prostředí.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-106">The update steps depend on your development environment.</span></span> <span data-ttu-id="2a4d7-107">Vyberte své prostředí z následujících částí.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-107">Choose your environment from the following sections.</span></span>

## <a name="python"></a><span data-ttu-id="2a4d7-108">Python</span><span class="sxs-lookup"><span data-stu-id="2a4d7-108">Python</span></span>

1. <span data-ttu-id="2a4d7-109">Aktualizace jádra `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="2a4d7-109">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="2a4d7-110">Ověření verze `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="2a4d7-110">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="2a4d7-111">Měl by se zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="2a4d7-111">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="2a4d7-112">Aktualizace balíčku `qsharp`</span><span class="sxs-lookup"><span data-stu-id="2a4d7-112">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="2a4d7-113">Ověření verze `qsharp`</span><span class="sxs-lookup"><span data-stu-id="2a4d7-113">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="2a4d7-114">Měl by se zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="2a4d7-114">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="2a4d7-115">Teď můžete pomocí aktualizované verze QDK spouštět stávající programy pro užívání.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-115">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="jupyter-notebooks"></a><span data-ttu-id="2a4d7-116">Poznámkové bloky Jupyter</span><span class="sxs-lookup"><span data-stu-id="2a4d7-116">Jupyter notebooks</span></span>

1. <span data-ttu-id="2a4d7-117">Aktualizace jádra `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="2a4d7-117">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="2a4d7-118">Ověření verze `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="2a4d7-118">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="2a4d7-119">Měl by se zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="2a4d7-119">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="2a4d7-120">Teď můžete otevřít existující Poznámkový blok Jupyter a spustit ho s aktualizovaným QDK.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-120">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="c-on-windows-using-visual-studio"></a><span data-ttu-id="2a4d7-121">C#ve Windows, pomocí sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2a4d7-121">C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="2a4d7-122">Aktualizace rozšíření Q # Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2a4d7-122">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="2a4d7-123">Visual Studio vás vyzve, abyste přijali aktualizace [rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) .</span><span class="sxs-lookup"><span data-stu-id="2a4d7-123">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="2a4d7-124">Přijmout aktualizaci</span><span class="sxs-lookup"><span data-stu-id="2a4d7-124">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="2a4d7-125">Šablony projektu jsou aktualizovány pomocí rozšíření.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-125">The project templates are updated with the extension.</span></span> <span data-ttu-id="2a4d7-126">Aktualizované šablony se vztahují pouze na nově vytvořené projekty.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-126">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="2a4d7-127">Kód pro existující projekty není aktualizován při aktualizaci rozšíření.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-127">The code for your existing projects is not updated when the extension is updated.</span></span>

1. <span data-ttu-id="2a4d7-128">Aktualizace balíčků QDK</span><span class="sxs-lookup"><span data-stu-id="2a4d7-128">Update the QDK packages</span></span>

    - <span data-ttu-id="2a4d7-129">Otevření existující aplikace</span><span class="sxs-lookup"><span data-stu-id="2a4d7-129">Open an existing application</span></span>
    - <span data-ttu-id="2a4d7-130">Vybrat **závislosti** v Průzkumník řešení</span><span class="sxs-lookup"><span data-stu-id="2a4d7-130">Select **Dependencies** in the Solution Explorer</span></span>
    - <span data-ttu-id="2a4d7-131">Výběr **možnosti spravovat balíčky NuGet**</span><span class="sxs-lookup"><span data-stu-id="2a4d7-131">Select **Manage NuGet Packages**</span></span>
    - <span data-ttu-id="2a4d7-132">Aktualizujte balíčky **Microsoft.** prodané na nejnovější verzi.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-132">Update the **Microsoft.Quantum** packages to the latest version</span></span>

1. <span data-ttu-id="2a4d7-133">Nyní můžete spustit aplikaci s nejnovějším QDK.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-133">You can now run your application with the latest QDK.</span></span>

## <a name="c-using-vs-code"></a><span data-ttu-id="2a4d7-134">C#, pomocí VS Code</span><span class="sxs-lookup"><span data-stu-id="2a4d7-134">C#, using VS Code</span></span>

1. <span data-ttu-id="2a4d7-135">Aktualizace rozšíření VS Code pro všechna pole</span><span class="sxs-lookup"><span data-stu-id="2a4d7-135">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="2a4d7-136">Restartovat VS Code</span><span class="sxs-lookup"><span data-stu-id="2a4d7-136">Restart VS Code</span></span>
    - <span data-ttu-id="2a4d7-137">Přejít na kartu **rozšíření**</span><span class="sxs-lookup"><span data-stu-id="2a4d7-137">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="2a4d7-138">Vyberte **Microsoft Quantum Development Kit pro rozšíření Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="2a4d7-138">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="2a4d7-139">Načíst znovu rozšíření</span><span class="sxs-lookup"><span data-stu-id="2a4d7-139">Reload the extension</span></span>

1. <span data-ttu-id="2a4d7-140">Aktualizace šablon projektů pro každé z nich:</span><span class="sxs-lookup"><span data-stu-id="2a4d7-140">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="2a4d7-141">Přejít na **zobrazení** -> **paleta příkazů**</span><span class="sxs-lookup"><span data-stu-id="2a4d7-141">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="2a4d7-142">Vyberte **Q #: Instalace šablon projektů**</span><span class="sxs-lookup"><span data-stu-id="2a4d7-142">Select **Q#: Install project templates**</span></span>

1. <span data-ttu-id="2a4d7-143">Otevřít existující aplikaci v VS Code</span><span class="sxs-lookup"><span data-stu-id="2a4d7-143">Open an existing application in VS Code</span></span>

   - <span data-ttu-id="2a4d7-144">Úpravou souboru. csproj přidejte nové verze balíčků.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-144">Edit the .csproj file to add the new package versions</span></span>

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    <span data-ttu-id="2a4d7-145">Pokud používáte další balíčky `Microsoft.Quantum`, aktualizujte je.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-145">If you use other `Microsoft.Quantum` packages, update these too.</span></span>

1. <span data-ttu-id="2a4d7-146">Teď můžete aplikaci spustit s aktualizovaným QDK</span><span class="sxs-lookup"><span data-stu-id="2a4d7-146">You can now run your application with the updated QDK</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="2a4d7-147">C#pomocí nástroje `dotnet`ho příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="2a4d7-147">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="2a4d7-148">Aktualizace šablon projektů pro každý produkt pro .NET</span><span class="sxs-lookup"><span data-stu-id="2a4d7-148">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="2a4d7-149">Aktualizace a spuštění existující aplikace</span><span class="sxs-lookup"><span data-stu-id="2a4d7-149">Update and run an existing application</span></span>

    - <span data-ttu-id="2a4d7-150">Aktualizace verzí balíčku QDK ve vaší aplikaci</span><span class="sxs-lookup"><span data-stu-id="2a4d7-150">Update the QDK package versions in your application</span></span>

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        <span data-ttu-id="2a4d7-151">Pokud vaše aplikace používá jiné balíčky `Microsoft.Quantum`, aktualizujte je.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-151">If your application uses any other `Microsoft.Quantum` packages, update these too.</span></span>

    - <span data-ttu-id="2a4d7-152">Spuštění aplikace</span><span class="sxs-lookup"><span data-stu-id="2a4d7-152">Run the application</span></span>

        ```bash
        dotnet run
        ```

    - <span data-ttu-id="2a4d7-153">Vaše aplikace se spustí s novými verzemi balíčků.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-153">Your application will run with the new package versions</span></span>

## <a name="whats-next"></a><span data-ttu-id="2a4d7-154">A co dál?</span><span class="sxs-lookup"><span data-stu-id="2a4d7-154">What's next?</span></span>

<span data-ttu-id="2a4d7-155">Teď, když jste v upřednostňovaném prostředí aktualizovali sadu pro vývoj pro práci s více operačními systémy, můžete pokračovat v vývoji a spouštění programů pro práci s více poli.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-155">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="2a4d7-156">Pokud jste ještě nezapsali program, můžete začít s [prvním programem pro práci](xref:microsoft.quantum.write-program)za sebou.</span><span class="sxs-lookup"><span data-stu-id="2a4d7-156">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
