---
title: Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035277"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Instalace sady Microsoft Quantum Development Kit (QDK)

Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK), abyste mohli začít s kvantovým programováním. Sada QDK obsahuje tyto komponenty:

- Programovací jazyk Q#
- Sada knihoven s abstraktními komplexními funkcemi v jazyku Q#
- Hostitelská aplikace (napsaná v Pythonu nebo v jazyku .NET), která spouští kvantové operace napsané v jazyku Q#
- Nástroje pro usnadnění vývoje

V závislosti na zvoleném vývojovém prostředí se provádějí rozdílné kroky instalace. V následujících částech vyberte požadované prostředí.

## <a name="develop-with-python"></a>Vývoj v Pythonu

1. Požadavky

    - [Python](https://www.python.org/downloads/) 3.6 nebo novější
    - Správce balíčků Pythonu [PIP](https://pip.pypa.io/en/stable/installing)
    - [.NET Core SDK 2.1 nebo novější](https://www.microsoft.com/net/download)

1. Nainstalujte balíček `iqsharp`.

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Nainstalujte balíček `qsharp`.

    ```bash
    pip install qsharp
    ```

1. Ověřte instalaci vytvořením aplikace `Hello World`.

    - Vytvořte minimální operaci v jazyku Q# tím, že vytvoříte soubor s názvem `Operation.qs` a do něj přidáte následující kód:

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - Vytvořte program v Pythonu s názvem `hello_world.py`, který bude volat operaci `SayHello()` jazyka Q#:

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - Spusťte program:

        ```bash
        python hello_world.py
        ```

    - Ověřte výstup. Výstupem programu by měly být následující řádky:

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a>Vývoj s využitím poznámkových bloků Jupyter

1. Požadavky

    - [Python](https://www.python.org/downloads/) 3.6 nebo novější
    - [Poznámkový blok Jupyter](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 2.1 nebo novější](https://www.microsoft.com/net/download)

1. Nainstalujte balíček `iqsharp`.

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Ověřte instalaci vytvořením aplikace `Hello World`.

    - Spusťte následující příkaz, kterým se spustí server poznámkového bloku:

        ```bash
        jupyter notebook
        ```

    - Přejděte na adresu URL zobrazenou na příkazovém řádku. Příklad: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

    - Vytvořte poznámkový blok Jupyter s použitím jádra Q# a do první buňky poznámkového bloku přidejte následující kód:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Spusťte tuto buňku poznámkového bloku:

        ![Buňka poznámkového bloku Jupyter](~/media/install-guide-jupyter.png)

        Ve výstupu buňky by se měl zobrazit text `SayHello`. Při spouštění v poznámkových blocích Jupyter se kompiluje kód v jazyku Q# a výstupem poznámkového bloku jsou názvy nalezených operací.

## <a name="develop-with-c-on-windows-using-visual-studio"></a>Vývoj v jazyku C# ve Windows s použitím sady Visual Studio

1. Požadavky

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 s povolenými úlohami vývoje pro různé platformy pomocí rozhraní .NET Core

1. Nainstalujte rozšíření sady Visual Studio pro jazyk Q#.

    - Stáhněte si [rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).
    - Přidejte rozšíření do sady Visual Studio.

1. Ověřte instalaci vytvořením aplikace `Hello World`.

    - Vytvořte novou aplikaci v jazyku Q#.

        - Přejděte do části **Soubor**  ->  **Nový**  ->  **Projekt**.
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

## <a name="develop-with-c-using-vs-code"></a>Vývoj v jazyku C# s využitím VS Code

1. Požadavky

   - [VS Code](https://code.visualstudio.com/download)
   - [.NET Core SDK 2.1 nebo novější](https://www.microsoft.com/net/download)

1. Nainstalujte rozšíření VS Code pro kvantové programování.

    - Nainstalujte [rozšíření VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

1. Nainstalujte šablony kvantového projektu:

   - Přejděte do části **Zobrazit** -> **Paleta příkazů**.
   - Vyberte **Q#: Nainstalovat šablony projektu**.

    Teď máte sadu Quantum Development Kit nainstalovanou a připravenou k používání ve vašich vlastních aplikacích a knihovnách.

1. Ověřte instalaci vytvořením aplikace `Hello World`.

    - Vytvořte nový projekt:

        - Přejděte do části **Zobrazit** -> **Paleta příkazů**.
        - Vyberte **Q#: Vytvořit nový projekt**.
        - Přejděte do umístění v systému souborů, ve kterém chcete aplikaci vytvořit.
        - Po vytvoření projektu klikněte na tlačítko **Otevřít nový projekt**.

    - Spusťte aplikaci:

        - Přejděte do části **Ladit** -> **Spustit bez ladění**.
        - V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`

> [!NOTE]
> * > * Rozšíření Visual Studio Code aktuálně nepodporuje pracovní prostory s více kořenovými složkami. Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a>Vývoj v jazyku C# s použitím nástroje pro příkazový řádek `dotnet`

1. Požadavky

    - [.NET Core SDK 2.1 nebo novější](https://www.microsoft.com/net/download)

1. Nainstalujte šablony kvantového projektu pro rozhraní .NET.

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    Teď máte sadu Quantum Development Kit nainstalovanou a připravenou k používání ve vašich vlastních aplikacích a knihovnách.

1. Ověřte instalaci vytvořením aplikace `Hello World`.

    - Vytvoření nové aplikace

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - Přejděte do adresáře nové aplikace.

       ```bash
       cd runSayHello
       ```

    Spolu se soubory projektu aplikace by se měly zobrazovat dva vytvořené soubory: soubor v jazyku Q# (`Operation.qs`) a soubor hostitele v jazyku C# (`Driver.cs`).

    - Spuštění aplikace

        ```bash
        dotnet run
        ```

        Měl by se zobrazit následující výstup: `Hello quantum world!`

## <a name="whats-next"></a>Co dále?

Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.write-program).
