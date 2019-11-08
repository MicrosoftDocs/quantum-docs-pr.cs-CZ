---
title: Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 580ac14f2e839d723884a96e9c5fd336ebcb5da0
ms.sourcegitcommit: 30fcb35986b43388ad65dfb876eb3ad8ad0533ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/07/2019
ms.locfileid: "73799151"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Instalace sady Microsoft Quantum Development Kit (QDK)

Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK), abyste mohli začít s kvantovým programováním. Sada QDK obsahuje tyto komponenty:

- Programovací jazyk Q#
- Sada knihoven s abstraktními komplexními funkcemi v jazyku Q#
- Hostitelská aplikace (napsaná v Pythonu nebo v jazyku .NET), která spouští kvantové operace napsané v jazyku Q#
- Nástroje pro usnadnění vývoje

V závislosti na zvoleném vývojovém prostředí se provádějí rozdílné kroky instalace. V následujících částech vyberte požadované prostředí.

## <a name="develop-with-python"></a>Vývoj v Pythonu

Balíček qsharp pro Python usnadňuje simulaci operací a funkcí jazyka Q# v rámci Pythonu. IQ# (anglicky se vyslovuje i-q-sharp) je rozšíření primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a simulaci operací v jazyce Q#.

1. Požadavky

    - [Python](https://www.python.org/downloads/) 3.6 nebo novější
    - Správce balíčků Pythonu [PIP](https://pip.pypa.io/en/stable/installing)
    - [.NET Core SDK 3.0 nebo novější](https://www.microsoft.com/net/download)

1. Nainstalujte balíček `qsharp`.

    ```bash
    pip install qsharp
    ```

1. Nainstalujte balíček `iqsharp`.

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
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

Poznámkové bloky Jupyter, které jsou oblíbené v akademickém prostředí, vědeckých laboratořích a také v rámci programování založeného na online spolupráci, nabízejí kromě pokynů, poznámek a dalšího obsahu také možnost místního spouštění kódu, nově včetně kódu v jazyce Q#.  Podívejte se, co všechno k vytváření vlastních poznámkových bloků v Q# potřebujete.

IQ# (anglicky se vyslovuje i-q-sharp) je rozšíření sady .NET Core SDK primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a simulaci operací v jazyce Q#.


1. Požadavky

    - [Python](https://www.python.org/downloads/) 3.6 nebo novější
    - [Poznámkový blok Jupyter](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.0 nebo novější](https://www.microsoft.com/net/download)

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

        ![Buňka poznámkového bloku Jupyter s využitím kódu Q#](~/media/install-guide-jupyter.png)

        Ve výstupu buňky by se měl zobrazit text `SayHello`. Při spouštění v poznámkových blocích Jupyter se kompiluje kód v jazyku Q# a výstupem poznámkového bloku jsou názvy nalezených operací.


    - V nové buňce simulujte spuštění právě vytvořené operace v kvantovém počítači, a to pomocí příkazu magic `%simulate`:

        ![Buňka poznámkového bloku Jupyter s využitím příkazu magic %simulate](~/media/install-guide-jupyter-simulate.png)

        Měla by se zobrazit zpráva na obrazovce spolu s výsledkem operace, kterou jste vyvolali (v tomto případě prázdným).


## <a name="develop-with-c-on-windows-using-visual-studio"></a>Vývoj v jazyku C# ve Windows s použitím sady Visual Studio

Visual Studio nabízí bohaté prostředí pro vývoj programů v Q# se skvělými funkcemi, jako je dokončování kódu a zvýrazňování syntaxe, které vývojářům pomáhají při vytváření aplikací.  Rozšíření Q# Visual Studio obsahuje šablony pro projekty a soubory v Q# a také zvýrazňování syntaxe a podporu technologie IntelliSense.


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

## <a name="develop-with-c-using-visual-studio-code"></a>Vývoj s využitím C# v editoru Visual Studio Code

Visual Studio Code (VS Code) nabízí bohaté prostředí pro vývoj programů v Q# napříč různými výpočetními prostředími, včetně systémů Windows, Linux a Mac, a poskytuje skvělé funkce, jako je dokončování kódu a zvýrazňování syntaxe, které vývojářům pomáhají při vytváření aplikací.  Rozšíření Q# VS Code obsahuje zvýrazňování syntaxe a fragmenty kódu v Q#.

1. Požadavky

   - [VS Code](https://code.visualstudio.com/download)
   - [.NET Core SDK 3.0 nebo novější](https://www.microsoft.com/net/download)

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

Samozřejmě můžete programy v Q# také sestavovat a spouštět z příkazového řádku. Stačí nainstalovat .NET Core SDK a šablony projektů QDK. 

1. Požadavky

    - [.NET Core SDK 3.0 nebo novější](https://www.microsoft.com/net/download)

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
