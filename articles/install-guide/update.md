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
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Aktualizace Microsoft Quantum Development Kit (QDK)

Přečtěte si, jak aktualizovat Microsoft Quantum Development Kit (QDK) na nejnovější verzi.

V tomto článku se předpokládá, že už máte nainstalované QDK. Pokud instalujete poprvé, přečtěte si [příručku k instalaci](xref:microsoft.quantum.install).


## <a name="updating-q-projects"></a>Aktualizují se projekty Q #. 

1. Nejprve nainstalujte nejnovější verzi [.NET Core SDK 3,0](https://dotnet.microsoft.com/download) a spusťte na příkazovém řádku následující příkaz:
```bash
dotnet --version
```
 Ověřte, že výstup je 3.0.100 nebo vyšší, a postupujte podle pokynů níže v závislosti na nastavení.

### <a name="in-visual-studio"></a>V nástroji Visual Studio
 
 1. Aktualizace na nejnovější verzi sady Visual Studio 2019 najdete [tady](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) pokyny.
 2. Otevřete řešení v aplikaci Visual Studio
 3. V nabídce vyberte sestavení > Vyčistit řešení. 
 4. [Aktualizujte cílové rozhraní](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) v každém z vašich souborů. csproj na netcoreapp 3.0 (nebo netstandard 2.1, pokud se jedná o projekt knihovny).
 5. Uložit a zavřít všechny soubory ve vašem řešení
 6. Vyberte nástroje > příkazového řádku > Developer Command Prompt
 7. Pro každý projekt v řešení spusťte následující příkaz:
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
Pokud vaše projekty používají jiné balíčky Microsoft., spusťte příkaz i pro tyto. 
 8. Zavřete příkazový řádek a vyberte sestavení Build > Build ( *nevybírejte znovu* sestavit řešení, protože opětovné sestavení se zpočátku nezdaří)

### <a name="in-visual-studio-code"></a>V Visual Studio Code

1. V Visual Studio Code otevřete složku obsahující projekt, který chcete aktualizovat.
1. Výběr terminálu > nového terminálu
1. Postupujte podle pokynů pro aktualizaci pomocí příkazového řádku.

### <a name="using-the-command-line"></a>Používání příkazového řádku

1. Přejděte do složky, která obsahuje soubor projektu.
2. Spusťte následující příkaz:
```bash
dotnet clean [project_name].csproj
```

3. [Aktualizujte cílové rozhraní](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) v každém z vašich souborů. csproj na netcoreapp 3.0 (nebo netstandard 2.1, pokud se jedná o projekt knihovny).
4. Spusťte následující příkaz:
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
Pokud váš projekt používá jiné balíčky Microsoft., spusťte příkaz pro tyto účely.

5. Uložit a zavřít všechny soubory
6. Opakujte 1-4 pro každou závislost projektu a pak přejděte zpátky do složky, která obsahuje váš hlavní projekt, a spusťte:
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a>Aktualizace SWEETIQ # pro Python

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
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
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
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. Z umístění souborů `.qs` spusťte následující příkaz
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. Teď můžete pomocí aktualizované verze QDK spouštět stávající programy pro užívání.

## <a name="update-iq-for-jupyter-notebooks"></a>Aktualizace SWEETIQ # pro notebooky Jupyter

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
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. Z buňky v Jupyter Notebook spusťte následující příkaz:
    ```
    %workspace reload
    ```

1. Teď můžete otevřít existující Poznámkový blok Jupyter a spustit ho s aktualizovaným QDK.

## <a name="update-visual-studio-qdk-extension"></a>Aktualizovat rozšíření sady Visual Studio QDK

1. Aktualizace rozšíření Q # Visual Studio

    - Visual Studio vás vyzve, abyste přijali aktualizace [rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) .
    - Přijmout aktualizaci

    > [!NOTE]
    > Šablony projektu jsou aktualizovány pomocí rozšíření. Aktualizované šablony se vztahují pouze na nově vytvořené projekty. Kód pro existující projekty není aktualizován při aktualizaci rozšíření.

## <a name="update-vs-code-qdk-extension"></a>Aktualizovat rozšíření VS Code QDK

1. Aktualizace rozšíření VS Code pro všechna pole

    - Restartovat VS Code
    - Přejít na kartu **rozšíření**
    - Vyberte **Microsoft Quantum Development Kit pro rozšíření Visual Studio Code**
    - Načíst znovu rozšíření

1. Aktualizace šablon projektů pro každé z nich:

   - Přejít na **zobrazení** -> **paleta příkazů**
   - Vyberte **Q #: Instalace šablon projektů**

## <a name="c-using-the-dotnet-command-line-tool"></a>C#pomocí nástroje `dotnet`ho příkazového řádku

1. Aktualizace šablon projektů pro každý produkt pro .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>A co dál?

Teď, když jste v upřednostňovaném prostředí aktualizovali sadu pro vývoj pro práci s více operačními systémy, můžete pokračovat v vývoji a spouštění programů pro práci s více poli. Pokud jste ještě nezapsali program, můžete začít s [prvním programem pro práci](xref:microsoft.quantum.write-program)za sebou.
