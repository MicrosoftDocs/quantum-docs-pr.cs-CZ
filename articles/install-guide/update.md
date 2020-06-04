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
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Aktualizace Microsoft Quantum Development Kit (QDK)

Přečtěte si, jak aktualizovat Microsoft Quantum Development Kit (QDK) na nejnovější verzi.

V tomto článku se předpokládá, že už máte nainstalované QDK. Pokud instalujete poprvé, přečtěte si [příručku k instalaci](xref:microsoft.quantum.install).

Doporučujeme, abyste si zachovali aktuálnost nejnovější verze QDK. Postupujte podle tohoto průvodce aktualizací a upgradujte na nejnovější verzi QDK. Proces se skládá ze dvou částí:
1. Aktualizace stávajících souborů a projektů Q # pro zarovnání kódu s aktualizovanou syntaxí.
2. Aktualizuje se QDK sám pro zvolené vývojové prostředí.

## <a name="updating-q-projects"></a>Aktualizují se projekty Q #. 

Bez ohledu na to, jestli používáte C# nebo Python k hostování operací Q #, postupujte podle těchto pokynů a aktualizujte své projekty Q #.

1. Nejdřív ověřte, že máte nejnovější verzi [.NET Core SDK 3,1](https://dotnet.microsoft.com/download). Spusťte na příkazovém řádku následující příkaz:

    ```dotnetcli
    dotnet --version
    ```

    Ověřte, že výstup je `3.1.100` nebo vyšší. Pokud ne, nainstalujte [nejnovější verzi](https://dotnet.microsoft.com/download) a zkuste to znovu. Pak postupujte podle pokynů níže v závislosti na instalaci (Visual Studio, Visual Studio Code nebo přímo na příkazovém řádku).

### <a name="update-q-projects-in-visual-studio"></a>Aktualizace projektů Q # v aplikaci Visual Studio
 
1. Aktualizujte na nejnovější verzi sady Visual Studio 2019, pokyny najdete [tady](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) .
2. Otevřete řešení v aplikaci Visual Studio.
3. V nabídce vyberte **sestavit**  ->  **Vyčištění řešení**.
4. V každém z vašich souborů. csproj aktualizujte cílové rozhraní na `netcoreapp3.1` (nebo `netstandard2.1` Pokud se jedná o projekt knihovny).
    To znamená upravit řádky formuláře:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Další podrobnosti o určení cílových rozhraní najdete [tady](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

5. V každém ze souborů. csproj nastavte sadu SDK na `Microsoft.Quantum.Sdk` , jak je uvedeno na řádku níže. Všimněte si, že číslo verze by mělo být nejnovější dostupné a můžete ho zjistit pomocí [poznámky k verzi](https://docs.microsoft.com/quantum/relnotes/).

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. Uložte a zavřete všechny soubory ve vašem řešení.

7. Vyberte **nástroje**  ->  **příkazového řádku**  ->  **Developer Command Prompt**. Alternativně můžete použít konzolu pro správu balíčků v sadě Visual Studio.

8. Pro každý projekt v řešení spusťte následující příkaz pro **Odebrání** tohoto balíčku:

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Pokud vaše projekty používají jakékoli jiné balíčky Microsoft. probíhat nebo Microsoft. Azure. (např. Microsoft. probíhat. NUMERIC), spusťte pro ně příkaz **Add** , který aktualizuje použitou verzi.

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. Zavřete příkazový řádek a vyberte **sestavení**  ->  **Build** Build (nevybírejte *not* znovu sestavit řešení).

Nyní můžete přeskočit k [aktualizaci rozšíření sady Visual Studio QDK](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Aktualizace projektů Q # v Visual Studio Code

1. V Visual Studio Code otevřete složku obsahující projekt, který chcete aktualizovat.
2. Vyberte **terminál**  ->  **Nový**terminál.
3. Postupujte podle pokynů pro aktualizaci pomocí příkazového řádku (přímo níže).

### <a name="update-q-projects-using-the-command-line"></a>Aktualizace projektů Q # pomocí příkazového řádku

1. Přejděte do složky, která obsahuje váš hlavní soubor projektu.

2. Spusťte následující příkaz:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Určete aktuální verzi QDK. Pokud ho chcete najít, můžete si přečíst [poznámky k verzi](https://docs.microsoft.com/quantum/relnotes/). Verze bude v podobném formátu `0.11.2006.207` .

4. V každém z vašich `.csproj` souborů Projděte následující kroky:

    - Aktualizujte cílové rozhraní na `netcoreapp3.1` (nebo `netstandard2.1` Pokud se jedná o projekt knihovny). To znamená upravit řádky formuláře:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        Další podrobnosti o určení cílových rozhraní najdete [tady](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

    - Nahraďte odkaz na sadu SDK v definici projektu. Ujistěte se, že číslo verze odpovídá hodnotě určené v **kroku 3**.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - Pokud je k dispozici, odeberte odkaz na balíček `Microsoft.Quantum.Development.Kit` , který bude zadán v následující položce:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - Aktualizujte verzi všech balíčků pro neplatnost od Microsoftu na nejnovější vydanou verzi QDK (stanovenou v **kroku 3**). Tyto balíčky jsou pojmenovány s následujícími vzory:

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        Odkazy na balíčky mají následující formát:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - Aktualizovaný soubor uložte.

    - Obnovte závislosti projektu následujícím způsobem:

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. Přejděte zpět do složky obsahující váš hlavní projekt a spusťte příkaz:

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Když se teď aktualizují projekty Q #, aktualizujte QDK sám podle pokynů níže.

## <a name="updating-the-qdk"></a>Aktualizace QDK

Proces aktualizace QDK se liší v závislosti na vašem vývojovém jazyce a prostředí.
Níže vyberte vývojové prostředí.

* [Python: aktualizace rozšíření SWEETIQ #](#update-iq-for-python)
* [Jupyter poznámkové bloky: aktualizace rozšíření SWEETIQ #](#update-iq-for-jupyter-notebooks)
* [Visual Studio: aktualizace rozšíření QDK](#update-visual-studio-qdk-extension)
* [VS Code: aktualizace rozšíření QDK](#update-vs-code-qdk-extension)
* [Příkazový řádek a C#: aktualizace šablon projektů](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Aktualizace SWEETIQ # pro Python

1. Aktualizace `iqsharp` jádra 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Ověření `iqsharp` verze

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Měl by se zobrazit následující výstup:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Nedělejte si starosti `iqsharp` , pokud je vaše verze vyšší, měla by odpovídat [nejnovější verzi](xref:microsoft.quantum.relnotes).

3. Aktualizace `qsharp` balíčku

    ```bash
    pip install qsharp --upgrade
    ```

4. Ověření `qsharp` verze

    ```bash
    pip show qsharp
    ```

    Měl by se zobrazit následující výstup:

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. Z umístění vašich souborů spusťte následující příkaz. `.qs`

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. Teď můžete pomocí aktualizované verze QDK spouštět stávající programy pro užívání.

### <a name="update-iq-for-jupyter-notebooks"></a>Aktualizace SWEETIQ # pro notebooky Jupyter

1. Aktualizace `iqsharp` jádra

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Ověření `iqsharp` verze

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Výstup by měl vypadat přibližně takto:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Nedělejte si starosti `iqsharp` , pokud je vaše verze vyšší, měla by odpovídat [nejnovější verzi](xref:microsoft.quantum.relnotes).

3. Z buňky v Jupyter Notebook spusťte následující příkaz:

    ```
    %workspace reload
    ```

4. Teď můžete otevřít existující Poznámkový blok Jupyter a spustit ho s aktualizovaným QDK.

### <a name="update-visual-studio-qdk-extension"></a>Aktualizovat rozšíření sady Visual Studio QDK

1. Aktualizace rozšíření Q # Visual Studio

    - Visual Studio vás vyzve, abyste přijali aktualizace [rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) .
    - Přijmout aktualizaci

    > [!NOTE]
    > Šablony projektu jsou aktualizovány pomocí rozšíření. Aktualizované šablony se vztahují pouze na nově vytvořené projekty. Kód pro existující projekty není aktualizován při aktualizaci rozšíření.

### <a name="update-vs-code-qdk-extension"></a>Aktualizovat rozšíření VS Code QDK

1. Aktualizace rozšíření VS Code pro všechna pole

    - Restartovat VS Code
    - Přejít na kartu **rozšíření**
    - Vyberte **Microsoft Quantum Development Kit pro rozšíření Visual Studio Code**
    - Načíst znovu rozšíření

2. Aktualizace šablon projektů pro každé z nich:

   - Přejít na **View**  ->  **paletu příkazů** zobrazení
   - Vyberte **Q #: Instalace šablon projektů**
   - Po několika sekundách byste měli obdržet místní nabídku potvrzující, že se šablony projektů úspěšně nainstalovaly.

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, použití `dotnet` nástroje příkazového řádku

1. Aktualizace šablon projektů pro každý produkt pro .NET

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
