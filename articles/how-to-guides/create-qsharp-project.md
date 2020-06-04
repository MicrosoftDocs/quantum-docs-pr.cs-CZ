---
title: 'Informace o tom, jak vytvořit projekt Q # pomocí QDK (pro vývoj pro všechna množství)'
description: 'Inicializujte projekt pro vývoj s využitím neQDKch a Q # ve vývojovém prostředí dle vašeho výběru.'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 8019b32a3290e2d45124ebb1eb75395f6cb758db
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327522"
---
# <a name="create-a-q-project-in-your-development-environment"></a>Vytvoření projektu Q # ve vývojovém prostředí

Naučte se vytvořit projekt Q # pomocí QDK.

Projekt Q # obsahuje soubory Q #, které obsahují kód doby a hostitelský program pro spouštění programu pro práci s více operačními systémy. Můžete napsat hostitelský program v jazycích .NET, jako je C# nebo v Pythonu. Můžete také spustit kód Q # v Jupyter Notebook pomocí jádra SWEETIQ #.

Vyberte vývojové prostředí a jazyk z následujících částí:

* [Python](#create-a-python-project)
* [Aplikace Jupyter Notebook v Q#](#create-a-q-jupyter-notebook-project)
* [C# se sadou Visual Studio](#create-a-c-project-on-windows-using-visual-studio)
* [C# s VS Code](#create-a-c-project-using-vs-code)
* [C# s příkazovým řádkem](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Vytvoření projektu v Pythonu

1. Požadavky

     * Instalace [sady pro vývoj pro](xref:microsoft.quantum.install.python) všechna tato prostředí pro Python

1. Vytvořte složku pro váš projekt a přejděte do této složky.

1. Vytvořte soubor Q # s názvem `Operation.qs` a přidejte do něj svůj kód q #. Příklad:

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. Vytvořte soubor hostitele Pythonu `host.py` s názvem pro volání operace Q #. Příklad:

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. Spusťte program:

    ```bash
    python host.py
    ```

1. Ověřte výstup. Výstupem programu by měly být následující řádky:

    ```bash
    Hello from quantum world!
    0
    ```

Nyní můžete pokračovat v vývoji programu pro práci s více.

## <a name="create-a-q-jupyter-notebook-project"></a>Vytvoření projektu Q # Jupyter Notebook

1. Požadavky

    * Nainstalujte si [pro Jupyter poznámkové bloky pro vývoj pro](xref:microsoft.quantum.install.jupyter) všechna ta.

1. Spusťte následující příkaz, kterým se spustí server poznámkového bloku:

    ```bash
    jupyter notebook
    ```

1. Přejděte na adresu URL zobrazenou na příkazovém řádku. Příklad: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]

1. V prohlížeči se zobrazí stránka Jupyter. Na kartě **soubory** vyberte **Nový**  >  **Q #** a vytvořte Jupyter notebook s jádrem Q #. Do první buňky poznámkového bloku přidejte následující kód:

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. Vyberte **buňky**  >  pro**spuštění** poznámkového bloku. `SayHello`brzy se zobrazí ve výstupu buňky:

    ![Jupyter Notebook buňka s kódem Q #](~/media/install-guide-jupyter.png)

    Při spuštění v poznámkových blocích Jupyter se zkompiluje kód Q # a výstup poznámkového bloku vytvoří název operací, které najde.

1. V nové buňce simulujte spuštění právě vytvořené operace v kvantovém počítači, a to pomocí příkazu magic `%simulate`:

    ![Jupyter Notebook buňka s% simulující Magic](~/media/install-guide-jupyter-simulate.png)

    Měla by se zobrazit zpráva na obrazovce spolu s výsledkem operace, kterou jste vyvolali (v tomto případě prázdným).

Nyní můžete přidat další operace Q #, abyste mohli pokračovat ve vývoji vašeho vlastního navýšení.

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Vytvoření projektu v jazyce C# ve Windows pomocí sady Visual Studio

1. Požadavky

    * Instalace [rozšíření pro vývojovou sadu pro Visual Studio](xref:microsoft.quantum.install.cs)

1. Vytvořte novou aplikaci v jazyku Q#.

    * Přejít na **soubor**  ->  **Nový**  ->  **projekt**
    * Do vyhledávacího pole zadejte `Q#`.
    * Vyberte **Aplikace Q#**.
    * Vybrat **Další**
    * Vyberte název a umístění aplikace.
    * Vyberte **vytvořit** .

1. Prozkoumejte projekt.

    Měli byste zjistit, že byly vytvořeny dva soubory: `Driver.cs`, což je hostitelská aplikace C#, a `Operation.qs`, což je program v jazyku Q#, který definuje jednoduchou operaci zobrazení zprávy na konzole.

1. Spuštění aplikace

    * Vyberte **ladit**  ->  **Spustit bez ladění**
    * V okně konzoly by se měl zobrazit text `Hello quantum world!`.

Nyní můžete pokračovat ve vývoji vašeho vlastního využití pomocí sady Visual Studio

> [!NOTE]
> * Pokud řešení sady Visual Studio obsahuje více projektů, musí se všechny projekty obsažené v řešení nacházet ve stejné složce jako řešení nebo v jedné z jejích podsložek.  

## <a name="create-a-c-project-using-vs-code"></a>Vytvoření projektu v jazyce C# pomocí VS Code

1. Požadavky

    * Instalace [rozšíření pro vývojovou sadu pro vs Code](xref:microsoft.quantum.install.cs)

1. Vytvořte nový projekt:

    * Přejít na **View**  ->  **paletu příkazů** zobrazení
    * Vyberte **Q #: vytvořit nový projekt.**
    * Vybrat **samostatnou konzolovou aplikaci**
    * Přejděte do umístění v systému souborů, ve kterém chcete aplikaci vytvořit.
    * Po vytvoření projektu klikněte na tlačítko **Otevřít nový projekt**.

1. Spusťte aplikaci:

    * Přejít na **terminál**  ->  **nový terminál**
    * Napište`dotnet run`
    * V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`

Nyní můžete pokračovat ve vývoji ve vaší práci pomocí Visual Studio Code.

> [!NOTE]
> * Rozšíření Visual Studio Code aktuálně nepodporuje pracovní prostory s více kořenovými složkami. Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>Vytvoření projektu v jazyce C# pomocí `dotnet` nástroje příkazového řádku

1. Požadavky

    * Instalace [sady pro vývoj pro všechna ta v příkazovém řádku](xref:microsoft.quantum.install.standalone)

1. Vytvoření nové aplikace

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. Přejděte do adresáře nové aplikace.

    ```bash
    cd <project name>
    ```

    Spolu se soubory projektu aplikace by se měly zobrazovat dva vytvořené soubory: soubor v jazyku Q# (`Operation.qs`) a soubor hostitele v jazyku C# (`Driver.cs`).

1. Spuštění aplikace

    ```dotnetcli
    dotnet run
    ```

    Měl by se zobrazit následující výstup: `Hello quantum world!`

Teď budete pokračovat ve vývoji ve vaší práci pomocí nástrojů příkazového řádku.

## <a name="next-steps"></a>Další kroky

Teď, když jste vytvořili projekt v upřednostňovaném prostředí, můžete pokračovat ve vývoji vašeho vlastního navýšení.
