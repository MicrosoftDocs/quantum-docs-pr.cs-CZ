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
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Aktualizace Microsoft Quantum Development Kit (QDK)

Přečtěte si, jak aktualizovat Microsoft Quantum Development Kit (QDK) na nejnovější verzi.

V tomto článku se předpokládá, že už máte nainstalované QDK. Pokud instalujete poprvé, přečtěte si [příručku k instalaci](xref:microsoft.quantum.install).

Postup aktualizace závisí na vašem vývojovém prostředí. Vyberte své prostředí z následujících částí.

## <a name="python"></a>Python

1. Aktualizace jádra `iqsharp`

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Ověření verze `iqsharp`

    ```bash
    dotnet iqsharp --version
    ```

    Měl by se zobrazit následující výstup:

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. Aktualizace balíčku `qsharp`

    ```bash
    pip install qsharp --upgrade
    ```

1. Ověření verze `qsharp`

    ```bash
    pip show qsharp
    ```

    Měl by se zobrazit následující výstup:

    ```bash
    Name: qsharp
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. Teď můžete pomocí aktualizované verze QDK spouštět stávající programy pro užívání.

## <a name="jupyter-notebooks"></a>Poznámkové bloky Jupyter

1. Aktualizace jádra `iqsharp`

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Ověření verze `iqsharp`

    ```bash
    dotnet iqsharp --version
    ```

    Měl by se zobrazit následující výstup:

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. Teď můžete otevřít existující Poznámkový blok Jupyter a spustit ho s aktualizovaným QDK.

## <a name="c-on-windows-using-visual-studio"></a>C#ve Windows, pomocí sady Visual Studio

1. Aktualizace rozšíření Q # Visual Studio

    - Visual Studio vás vyzve, abyste přijali aktualizace [rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) .
    - Přijmout aktualizaci

    > [!NOTE]
    > Šablony projektu jsou aktualizovány pomocí rozšíření. Aktualizované šablony se vztahují pouze na nově vytvořené projekty. Kód pro existující projekty není aktualizován při aktualizaci rozšíření.

1. Aktualizace balíčků QDK

    - Otevření existující aplikace
    - Vybrat **závislosti** v Průzkumník řešení
    - Výběr **možnosti spravovat balíčky NuGet**
    - Aktualizujte balíčky **Microsoft.** prodané na nejnovější verzi.

1. Nyní můžete spustit aplikaci s nejnovějším QDK.

## <a name="c-using-vs-code"></a>C#, pomocí VS Code

1. Aktualizace rozšíření VS Code pro všechna pole

    - Restartovat VS Code
    - Přejít na kartu **rozšíření**
    - Vyberte **Microsoft Quantum Development Kit pro rozšíření Visual Studio Code**
    - Načíst znovu rozšíření

1. Aktualizace šablon projektů pro každé z nich:

   - Přejít na **zobrazení** -> **paleta příkazů**
   - Vyberte **Q #: Instalace šablon projektů**

1. Otevřít existující aplikaci v VS Code

   - Úpravou souboru. csproj přidejte nové verze balíčků.

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    Pokud používáte další balíčky `Microsoft.Quantum`, aktualizujte je.

1. Teď můžete aplikaci spustit s aktualizovaným QDK

## <a name="c-using-the-dotnet-command-line-tool"></a>C#pomocí nástroje `dotnet`ho příkazového řádku

1. Aktualizace šablon projektů pro každý produkt pro .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. Aktualizace a spuštění existující aplikace

    - Aktualizace verzí balíčku QDK ve vaší aplikaci

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        Pokud vaše aplikace používá jiné balíčky `Microsoft.Quantum`, aktualizujte je.

    - Spuštění aplikace

        ```bash
        dotnet run
        ```

    - Vaše aplikace se spustí s novými verzemi balíčků.

## <a name="whats-next"></a>A co dál?

Teď, když jste v upřednostňovaném prostředí aktualizovali sadu pro vývoj pro práci s více operačními systémy, můžete pokračovat v vývoji a spouštění programů pro práci s více poli. Pokud jste ještě nezapsali program, můžete začít s [prvním programem pro práci](xref:microsoft.quantum.write-program)za sebou.
