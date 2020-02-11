---
title: 'Vývoj s Q # +C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 7803846279f230f5fc0ee8424bd39be735a650ca
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036283"
---
# <a name="develop-with-q--c"></a>Vývoj s Q # +C#

Nainstalujte QDK pro vývoj C# hostitelských programů pro volání Q # Operations.

Q # je sestavený tak, aby se dobře hrál s jazyky C#.NET – konkrétně. S tímto párováním můžete pracovat v různých vývojových prostředích:

- [Q # + C# s použitím sady Visual Studio (Windows)](#VS)
- [Q # + C# použití Visual Studio Code (Windows, Linux a Mac)](#VSC)
- [Q # + C# použití nástroje příkazového řádku `dotnet`](#command)

## Vývoj pomocí Q # + C# pomocí sady Visual Studio <a name="VS"></a>

Visual Studio nabízí bohatá prostředí pro vývoj programů Q #. Rozšíření Visual Studio Q # obsahuje šablony pro soubory a projekty Q # a také zvýrazňování syntaxe, dokončování kódu a podporu technologie IntelliSense.


1. Požadavky

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 s povolenými úlohami vývoje pro různé platformy pomocí rozhraní .NET Core

1. Nainstalujte rozšíření sady Visual Studio pro jazyk Q#.

    - Stažení a instalace [rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)

1. Ověřte instalaci vytvořením aplikace `Hello World`.

    - Vytvořte novou aplikaci v jazyku Q#.

        - Přejděte do části **Soubor** -> **Nový** -> **Projekt**.
        - Do vyhledávacího pole zadejte `Q#`.
        - Vyberte **Aplikace Q#** .
        - Vyberte **Další**.
        - Vyberte název a umístění aplikace.
        - Vyberte **Vytvořit**.

    - Prozkoumejte projekt.

        Měli byste zjistit, že byly vytvořeny dva soubory: `Driver.cs`, což je hostitelská aplikace C#, a `Operation.qs`, což je program v jazyku Q#, který definuje jednoduchou operaci zobrazení zprávy na konzole.

    - Spuštění aplikace

        - Vyberte **Ladit** -> **Spustit bez ladění**.
        - V okně konzoly by se měl zobrazit text `Hello quantum world!`.

> [!NOTE]
> * Pokud řešení sady Visual Studio obsahuje více projektů, musí se všechny projekty obsažené v řešení nacházet ve stejné složce jako řešení nebo v jedné z jejích podsložek.  

## Vývoj pomocí Q # + C# pomocí Visual Studio Code <a name="VSC"></a>

Visual Studio Code (VS Code) nabízí bohatý prostředí pro vývoj programů Q # v systémech Windows, Linux a Mac.  Rozšíření Q # VS Code zahrnuje podporu zvýrazňování syntaxe Q #, dokončování kódu a fragmentů kódu Q #.

1. Požadavky

   - [VS Code](https://code.visualstudio.com/download)
   - [.NET Core SDK 3,1 nebo novější](https://www.microsoft.com/net/download)

1. Nainstalujte rozšíření VS Code pro kvantové programování.

    - Nainstalujte [rozšíření VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

1. Nainstalujte šablony kvantového projektu:

   - Přejděte do části **Zobrazit** -> **Paleta příkazů**.
   - Vyberte **Q #: Instalace šablon projektů**

    Teď máte sadu Quantum Development Kit nainstalovanou a připravenou k používání ve vašich vlastních aplikacích a knihovnách.

1. Ověřte instalaci vytvořením aplikace `Hello World`.

    - Vytvořte nový projekt:

        - Přejděte do části **Zobrazit** -> **Paleta příkazů**.
        - Vyberte **Q #: vytvořit nový projekt.**
        - Vybrat **samostatnou konzolovou aplikaci**
        - Přejděte do umístění v systému souborů, ve kterém chcete aplikaci vytvořit.
        - Po vytvoření projektu klikněte na tlačítko **Otevřít nový projekt**.

    - Pokud ještě nemáte nainstalované C# rozšíření pro vs Code, zobrazí se automaticky otevírané okno. Nainstalujte rozšíření. 

    - Spusťte aplikaci:

        - Přejít na **terminál** -> **nový terminál**
        - Zadejte `dotnet run`
        - V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`


> [!NOTE]
> * Rozšíření Visual Studio Code aktuálně nepodporuje pracovní prostory s více kořenovými složkami. Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.

## Vývoj pomocí Q # + C# pomocí nástroje příkazového řádku `dotnet`<a name="command"></a>

Samozřejmě můžete programy v Q# také sestavovat a spouštět z příkazového řádku. Stačí nainstalovat .NET Core SDK a šablony projektů QDK. 

1. Požadavky

    - [.NET Core SDK 3,1 nebo novější](https://www.microsoft.com/net/download)

1. Nainstalujte šablony kvantového projektu pro rozhraní .NET.

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    Teď máte sadu Quantum Development Kit nainstalovanou a připravenou k používání ve vašich vlastních aplikacích a knihovnách.

1. Ověřte instalaci vytvořením aplikace `Hello World`.

    - Vytvoření nové aplikace

       ```dotnetcli
       dotnet new console -lang "Q#" -o runSayHello
       ```

    - Přejděte do adresáře nové aplikace.

       ```bash
       cd runSayHello
       ```

    Spolu se soubory projektu aplikace by se měly zobrazovat dva vytvořené soubory: soubor v jazyku Q# (`Operation.qs`) a soubor hostitele v jazyku C# (`Driver.cs`).

    - Spuštění aplikace

        ```dotnetcli
        dotnet run
        ```

        Měl by se zobrazit následující výstup: `Hello quantum world!`

    
## <a name="whats-next"></a>Co dále?

Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.write-program).
