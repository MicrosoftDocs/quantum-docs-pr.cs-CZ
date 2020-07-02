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
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Aktualizace sady Microsoft Quantum Development Kit (QDK)

Přečtěte si, jak aktualizovat sadu Microsoft Quantum Development Kit (QDK) na nejnovější verzi.

Tento článek předpokládá, že už máte sadu QDK nainstalovanou. Pokud ji instalujete poprvé, přečtěte si informace v [průvodci instalací](xref:microsoft.quantum.install).

Doporučujeme, abyste sadu QDK udržovali stále aktuální. Podle tohoto průvodce upgradujte na nejnovější verzi sady QDK. Proces se skládá ze dvou částí:
1. Aktualizace stávajících souborů a projektů Q# podle aktualizované syntaxe.
2. Aktualizace samotné sady QDK pro zvolené vývojové prostředí.

## <a name="updating-q-projects"></a>Aktualizace projektů Q#. 

Své projekty Q# aktualizujte podle těchto pokynů bez ohledu na to, jestli k hostování operací Q# používáte jazyk C#, nebo Python.

1. Nejdřív ověřte, že máte nejnovější verzi [.NET Core SDK 3.1](https://dotnet.microsoft.com/download). Na příkazovém řádku spusťte následující příkaz:

    ```dotnetcli
    dotnet --version
    ```

    Zkontrolujte, že výsledek je `3.1.100` nebo vyšší. Pokud ne, nainstalujte [nejnovější verzi](https://dotnet.microsoft.com/download) a zkontrolujte ji znovu. Pak postupujte podle pokynů níže v závislosti na vaší instalaci (Visual Studio, Visual Studio Code nebo přímo na příkazovém řádku).

### <a name="update-q-projects-in-visual-studio"></a>Aktualizace projektů Q# v sadě Visual Studio
 
1. Aktualizujte na nejnovější verzi sady Visual Studio 2019, pokyny najdete [zde](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019).
2. Otevřete své řešení v prostředí Visual Studio.
3. V nabídce vyberte **Kompilovat** -> **Vyčistit řešení**.
4. V každém z vašich souborů .csproj aktualizujte cílovou architekturu na `netcoreapp3.1` (nebo `netstandard2.1`, pokud se jedná o projekt knihovny).
    To znamená upravit řádky formuláře:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Další podrobnosti o určení cílových architektur [najdete zde](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

5. V každém ze souborů. csproj nastavte sadu SDK na `Microsoft.Quantum.Sdk`, jak je uvedeno na řádku níže. Všimněte si, že číslo verze by mělo být nejnovější dostupné a můžete ho zjistit z [poznámek k verzi](https://docs.microsoft.com/quantum/relnotes/).

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. Uložte a zavřete všechny soubory ve vašem řešení.

7. Vyberte **Nástroje** -> **Příkazový řádek** -> **Developer Command Prompt**. Můžete případně použít i konzolu pro správu balíčků v sadě Visual Studio.

8. Pro každý projekt v řešení spusťte následující příkaz, který **odstraní** tento balíček:

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Pokud vaše projekty používají jakékoli jiné balíčky Microsoft.Quantum nebo Microsoft.Azure.Quantum (např. Microsoft.Quantum.Numerics), příkazem **add** aktualizujte jejich použité verze.

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. Zavřete příkazový řádek a zvolte **Kompilovat** -> **Kompilovat řešení** (*nevybírejte* Znovu zkompilovat řešení).

Nyní můžete přeskočit na [aktualizaci rozšíření sady Visual Studio QDK](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Aktualizace projektů Q# v sadě Visual Studio Code

1. V sadě Visual Studio Code otevřete složku obsahující projekt, který chcete aktualizovat.
2. Vyberte **Terminál** -> **Nový Terminál**.
3. Postupujte podle následujících pokynů pro aktualizaci pomocí příkazového řádku.

### <a name="update-q-projects-using-the-command-line"></a>Aktualizace projektů Q# pomocí příkazového řádku

1. Přejděte do složky, která obsahuje váš hlavní soubor projektu.

2. Spusťte následující příkaz:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Určete aktuální verzi sady QDK. Zjistíte ho třeba v [poznámkách k verzi](https://docs.microsoft.com/quantum/relnotes/). Verze bude mít tvar `0.11.2006.207`.

4. V každém ze souborů `.csproj` proveďte následující postup:

    - Aktualizujte cílovou architekturu na `netcoreapp3.1` (nebo `netstandard2.1`, pokud se jedná o projekt knihovny). To znamená upravit řádky formuláře:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        Další podrobnosti o určení cílových architektur [najdete zde](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

    - Nahraďte odkaz na sadu SDK v definici projektu. Ujistěte se, že číslo verze odpovídá hodnotě zjištěné v **kroku 3**.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - Pokud existuje, odeberte odkaz na balíček `Microsoft.Quantum.Development.Kit`, který bude zadán v následující položce:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - Aktualizujte verzi všech balíčků Microsoft Quantum na nejnovější vydanou verzi QDK (zjištěnou v **kroku 3**). Tyto balíčky mají názvy v následujícím tvaru:

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        Odkazy na balíčky mají následující tvar:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - Aktualizovaný soubor uložte.

    - Obnovte závislosti projektu následujícím postupem:

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. Přejděte zpět do složky, která obsahuje váš hlavní projekt, a spusťte příkaz:

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Když teď máte aktualizované projekty Q#, podle následujících pokynů aktualizujte samotnou sadu QDK.

## <a name="updating-the-qdk"></a>Aktualizace sady QDK

Proces aktualizace sady QDK se liší v závislosti na vašem vývojovém jazyce a prostředí.
Vyberte své vývojové prostředí níže.

* [Python: aktualizace rozšíření IQ#](#update-iq-for-python)
* [Jupyter Notebooks: aktualizace rozšíření IQ#](#update-iq-for-jupyter-notebooks)
* [Visual Studio: aktualizace rozšíření QDK](#update-visual-studio-qdk-extension)
* [VS Code: aktualizace rozšíření QDK](#update-vs-code-qdk-extension)
* [Příkazový řádek a C#: aktualizace šablon projektů](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Aktualizace IQ# pro Python

1. Aktualizujte jádro `iqsharp` 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Ověřte verzi `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Měl by se zobrazit následující výstup:

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Nedělejte si starosti, pokud je verze `iqsharp` vyšší, měla by odpovídat [nejnovějšímu vydání](xref:microsoft.quantum.relnotes).

3. Aktualizujte balíček `qsharp`

    ```
    pip install qsharp --upgrade
    ```

4. Ověřte verzi `qsharp`

    ```
    pip show qsharp
    ```

    Měl by se zobrazit následující výstup:

    ```
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. Ve složce, kde jsou umístěné soubory `.qs`, spusťte následující příkaz

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. Teď můžete pomocí aktualizované verze QDK zkusit spustit své kvantové programy.

### <a name="update-iq-for-jupyter-notebooks"></a>Aktualizace IQ# pro Jupyter Notebooks

1. Aktualizujte jádro `iqsharp`

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Ověřte verzi `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Výstup by měl vypadat přibližně takto:

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Nedělejte si starosti, pokud je verze `iqsharp` vyšší, měla by odpovídat [nejnovějšímu vydání](xref:microsoft.quantum.relnotes).

3. Z buňky v poznámkovém bloku Jupyter spusťte následující příkaz:

    ```
    %workspace reload
    ```

4. Teď můžete otevřít existující Poznámkový blok Jupyter a spustit ho s aktualizovanou sadou QDK.

### <a name="update-visual-studio-qdk-extension"></a>Aktualizace rozšíření QDK sady Visual Studio

1. Aktualizujte rozšíření Q# sady Visual Studio

    - Visual Studio vás vyzve, abyste přijali aktualizace [rozšíření Quantum sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).
    - Přijměte aktualizaci.

    > [!NOTE]
    > Šablony projektu budou aktualizovány spolu s rozšířením. Aktualizované šablony se uplatní jen na nově vytvořené projekty. Kód stávajících projektů se při aktualizaci rozšíření nezmění.

### <a name="update-vs-code-qdk-extension"></a>Aktualizace rozšíření QDK sady VS Code

1. Aktualizujte rozšíření QDK sady VS Code

    - Restartujte VS Code
    - Přejděte na kartu **Rozšíření**.
    - Vyberte rozšíření **Microsoft Quantum Development Kit pro Visual Studio Code**.
    - Znovu načtěte rozšíření.

2. Aktualizujte šablony projektu Quantum:

   - Přejděte do části **Zobrazit** -> **Paleta příkazů**.
   - Vyberte **Q#: Nainstalovat šablony projektu**.
   - Po několika sekundách byste měli vidět okno potvrzující, že se šablony projektů úspěšně nainstalovaly.

### <a name="c-using-the-dotnet-command-line-tool"></a>C# s použitím nástroje příkazového řádku `dotnet`.

1. Aktualizujte šablony projektu Quantum pro rozhraní .NET.

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```