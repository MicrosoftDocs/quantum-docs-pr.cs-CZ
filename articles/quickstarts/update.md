---
title: Aktualizace sady Quantum Development Kit (QDK)
description: Tento článek popisuje aktualizaci projektů v Q# a sady Microsoft Quantum Development Kit na aktuální verzi.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
no-loc:
- Q#
- $$v
ms.openlocfilehash: dd7360961aa728a6aa63b8d8c4e4840f5bf2afe8
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866753"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Aktualizace sady Microsoft Quantum Development Kit (QDK)

Přečtěte si, jak aktualizovat sadu Microsoft Quantum Development Kit (QDK) na nejnovější verzi.

Tento článek předpokládá, že už máte sadu QDK nainstalovanou. Pokud ji instalujete poprvé, přečtěte si informace v [průvodci instalací](xref:microsoft.quantum.install).

Doporučujeme, abyste sadu QDK udržovali stále aktuální. Podle tohoto průvodce upgradujte na nejnovější verzi sady QDK. Proces se skládá ze dvou částí:
1. Aktualizace stávajících souborů a projektů v Q# podle aktualizované syntaxe.
2. Aktualizace samotné sady QDK pro zvolené vývojové prostředí.

## <a name="updating-no-locq-projects"></a>Aktualizace projektů v Q# 

Své projekty v Q# aktualizujte podle těchto pokynů bez ohledu na to, jestli k hostování operací Q# používáte jazyk C#, nebo Python.

1. Nejdřív ověřte, že máte nejnovější verzi [.NET Core SDK 3.1](https://dotnet.microsoft.com/download). Na příkazovém řádku spusťte následující příkaz:

    ```dotnetcli
    dotnet --version
    ```

    Zkontrolujte, že výsledek je `3.1.100` nebo vyšší. Pokud ne, nainstalujte [nejnovější verzi](https://dotnet.microsoft.com/download) a zkontrolujte ji znovu. Pak postupujte podle pokynů níže v závislosti na vaší instalaci (Visual Studio, Visual Studio Code nebo přímo na příkazovém řádku).

### <a name="update-no-locq-projects-in-visual-studio"></a>Aktualizace projektů v Q# v sadě Visual Studio
 
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
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
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


### <a name="update-no-locq-projects-in-visual-studio-code"></a>Aktualizace projektů v Q# v editoru Visual Studio Code

1. V sadě Visual Studio Code otevřete složku obsahující projekt, který chcete aktualizovat.
2. Vyberte **Terminál** -> **Nový Terminál**.
3. Postupujte podle následujících pokynů pro aktualizaci pomocí příkazového řádku.

### <a name="update-no-locq-projects-using-the-command-line"></a>Aktualizace projektů v Q# pomocí příkazového řádku

1. Přejděte do složky, která obsahuje váš hlavní soubor projektu.

2. Spusťte následující příkaz:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Určete aktuální verzi sady QDK. Zjistíte ho třeba v [poznámkách k verzi](https://docs.microsoft.com/quantum/relnotes/). Verze bude mít tvar `0.12.20072031`.

4. V každém ze souborů `.csproj` proveďte následující postup:

    - Aktualizujte cílovou architekturu na `netcoreapp3.1` (nebo `netstandard2.1`, pokud se jedná o projekt knihovny). To znamená upravit řádky formuláře:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        Další podrobnosti o určení cílových architektur [najdete zde](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

    - Nahraďte odkaz na sadu SDK v definici projektu. Ujistěte se, že číslo verze odpovídá hodnotě zjištěné v **kroku 3**.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
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
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
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

Když teď máte projekty v Q# aktualizované, podle následujících pokynů aktualizujte samotnou sadu QDK.

## <a name="updating-the-qdk"></a>Aktualizace sady QDK

Proces aktualizace sady QDK se liší v závislosti na vašem vývojovém jazyce a prostředí.
Vyberte své vývojové prostředí níže.

* [Python: aktualizace balíčku `qsharp`](#update-the-qsharp-python-package)
* [Aplikace Jupyter Notebook: aktualizace jádra IQ#](#update-the-iq-jupyter-kernel)
* [Visual Studio: aktualizace rozšíření QDK](#update-visual-studio-qdk-extension)
* [VS Code: aktualizace rozšíření QDK](#update-vs-code-qdk-extension)
* [Příkazový řádek a C#: aktualizace šablon projektů](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a>Aktualizace balíčku Pythonu `qsharp`

Postup aktualizace závisí na tom, jestli jste původně provedli instalaci pomocí prostředí conda, nebo pomocí rozhraní .NET CLI a pip.

#### <a name="update-using-conda-recommended"></a>[Aktualizace pomocí prostředí conda (doporučeno)](#tab/tabid-conda)

1. Aktivujte prostředí conda, do kterého jste nainstalovali balíček `qsharp`, a potom proveďte aktualizaci spuštěním tohoto příkazu:

    ```
    conda update -c quantum-engineering qsharp
    ```

1. Ve složce, kde jsou umístěné soubory `.qs`, spusťte následující příkaz:

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[Aktualizace pomocí rozhraní .NET CLI a pip (rozšířené)](#tab/tabid-dotnetcli)

1. Aktualizujte jádro `iqsharp` 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Ověřte verzi `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Měl by se zobrazit následující výstup:

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    Nedělejte si starosti, pokud je vaše verze `iqsharp` vyšší. Měla by odpovídat [nejnovější verzi](xref:microsoft.quantum.relnotes).

1. Aktualizujte balíček `qsharp`:

    ```
    pip install qsharp --upgrade
    ```

1. Ověřte verzi `qsharp`:

    ```
    pip show qsharp
    ```

    Měl by se zobrazit následující výstup:

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. Ve složce, kde jsou umístěné soubory `.qs`, spusťte následující příkaz:

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

Teď můžete pomocí aktualizovaného balíčku Pythonu `qsharp` zkusit spustit své kvantové programy.

### <a name="update-the-ino-locq-jupyter-kernel"></a>Aktualizace jádra IQ# Jupyter

Postup aktualizace závisí na tom, jestli jste původně provedli instalaci pomocí prostředí conda, nebo pomocí rozhraní .NET CLI a pip.

#### <a name="update-using-conda-recommended"></a>[Aktualizace pomocí prostředí conda (doporučeno)](#tab/tabid-conda)

1. Aktivujte prostředí conda, do kterého jste nainstalovali balíček `qsharp`, a potom proveďte aktualizaci spuštěním tohoto příkazu:

    ```
    conda update -c quantum-engineering qsharp
    ```

1. Z buňky v každé aplikaci Jupyter Notebook s podporou Q# spusťte následující příkaz:

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[Aktualizace pomocí rozhraní .NET CLI a pip (rozšířené)](#tab/tabid-dotnetcli)

1. Aktualizujte balíček `Microsoft.Quantum.IQSharp`:

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Ověřte verzi `iqsharp`:

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Výstup by měl vypadat přibližně takto:

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    Nedělejte si starosti, pokud je vaše verze `iqsharp` vyšší. Měla by odpovídat [nejnovější verzi](xref:microsoft.quantum.relnotes).

1. Z buňky v každé aplikaci Jupyter Notebook s podporou Q# spusťte následující příkaz:

    ```
    %workspace reload
    ```

***

Teď můžete pomocí aktualizovaného jádra IQ# spustit stávající služby Jupyter Notebook s podporou Q#.

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

### <a name="c-using-the-dotnet-command-line-tool"></a>C# s použitím nástroje příkazového řádku `dotnet`.

1. Aktualizujte šablony projektu Quantum pro rozhraní .NET.

    Z příkazového řádku:

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   Případně pokud máte v úmyslu používat šablony příkazového řádku a už máte nainstalované rozšíření VS Code QDK, můžete aktualizovat šablony projektu ze samotného rozšíření:

   - [Aktualizace rozšíření QDK](#update-vs-code-qdk-extension)
   - V editoru VS Code přejděte do části **Zobrazit** -> **Paleta příkazů**.
   - Vyberte **Q#: Instalace šablon projektů pro příkazový řádek**.
   - Po několika sekundách byste měli vidět okno potvrzující, že se šablony projektů úspěšně nainstalovaly.
