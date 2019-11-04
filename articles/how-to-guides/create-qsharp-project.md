---
title: 'Informace o tom, jak vytvořit projekt Q # pomocí QDK (pro vývoj pro všechna množství)'
description: 'Inicializujte projekt pro vývoj s využitím neQDKch a Q # ve vývojovém prostředí dle vašeho výběru.'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: b4bec5e7a174b7e2d588331dd2093c7b23a728b0
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444170"
---
# <a name="create-a-q-project-in-your-development-environment"></a>Vytvoření projektu Q # ve vývojovém prostředí

Naučte se vytvořit projekt Q # pomocí QDK.

Projekt Q # obsahuje soubory Q #, které obsahují kód doby a hostitelský program pro spouštění programu pro práci s více operačními systémy. Hostitelský program můžete napsat v jazycích .NET C#, jako je, nebo v Pythonu. Můžete také spustit kód Q # v poznámkovém bloku Jupyter pomocí jádra SWEETIQ #.

Vyberte vývojové prostředí a jazyk z následujících částí:

* [Python](#create-a-python-project)
* [Jupyter poznámkové bloky](#create-a-jupyter-notebook-project)
* [C#se sadou Visual Studio](#create-a-c-project-on-windows-using-visual-studio)
* [C#s VS Code](#create-a-c-project-using-vs-code)
* [C#pomocí příkazového řádku](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Vytvoření projektu v Pythonu

1. Požadavky

     * [Sada pro vývoj pro](xref:microsoft.quantum.install#develop-with-python) všechna tato prostředí pro Python

1. Vytvořte složku pro váš projekt a přejděte do této složky.

1. Vytvořte soubor Q # s názvem `Operation.qs`a přidejte do něj svůj kód Q #. Například:

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

1. Vytvořte soubor hostitele Pythonu s názvem `host.py` pro volání operace Q #. Například:

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. Spusťte program:

    ```bash
    python host.py
    ```

1. Ověřte výstup. Program by měl mít výstup na následujících řádcích:

    ```bash
    Hello from quantum world!
    0
    ```

Nyní můžete pokračovat v vývoji programu pro práci s více.

## <a name="create-a-jupyter-notebook-project"></a>Vytvoření projektu Jupyter Notebook

1. Požadavky

    * [Vývojová sada pro všechna ta – Jupyter poznámkové bloky](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)

1. Spusťte následující příkaz, který spustí Poznámkový Server:

    ```bash
    jupyter notebook
    ```

1. Přejděte na adresu URL zobrazenou na příkazovém řádku. Například: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

1. V prohlížeči se zobrazí stránka Jupyter. Na kartě **soubory** vyberte **Nový** > **Q #** a vytvořte Poznámkový blok Jupyter s jádrem Q #. Do první buňky poznámkového bloku přidejte následující kód:

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. Vyberte **buňku** > **Spustit buňky** pro spuštění poznámkového bloku. `SayHello` se brzy objeví ve výstupu buňky:

    ![Buňka Jupyter Poznámkový blok s kódem Q #](~/media/install-guide-jupyter.png)

    Při spuštění v poznámkových blocích Jupyter se zkompiluje kód Q # a výstup poznámkového bloku vytvoří název operací, které najde.

1. V nové buňce Simulujte spuštění v počítačovém provozu operace, kterou jste právě vytvořili, pomocí `%simulate` Magic:

    ![Buňka Jupyter poznámkového bloku s% simuluje Magic](~/media/install-guide-jupyter-simulate.png)

    Měla by se zobrazit zpráva vytištěná na obrazovce spolu s výsledkem operace, kterou jste vyvolali (v tomto případě je to prázdné).

Nyní můžete přidat další operace Q #, abyste mohli pokračovat ve vývoji vašeho vlastního navýšení.

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Vytvoření C# projektu ve Windows pomocí sady Visual Studio

1. Požadavky

    * [Sada pro vývoj pro všechna tato prostředí pro Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)

1. Vytvoří novou aplikaci Q #.

    * Přejít na **soubor** -> **Nový** -> **projekt**
    * Do vyhledávacího pole zadejte `Q#`
    * Vybrat **aplikaci Q #**
    * Vyberte **Další**.
    * Zvolit název a umístění vaší aplikace
    * Vyberte **Vytvořit**.

1. Kontrola projektu

    Měli byste vidět, že byly vytvořeny dva soubory: `Driver.cs`, což je C# hostitelská aplikace; a `Operation.qs`, což je program Q #, který definuje jednoduchou operaci pro tisk zprávy do konzoly.

1. Spuštění aplikace

    * Vyberte **ladění** -> **Spustit bez ladění**
    * Měl by se zobrazit text `Hello quantum world!` vytištěný v okně konzoly.

Nyní můžete pokračovat ve vývoji vašeho vlastního využití pomocí sady Visual Studio

> [!NOTE]
> * Pokud máte více projektů v rámci jednoho řešení sady Visual Studio, všechny projekty, které jsou obsaženy v řešení, musí být ve stejné složce jako řešení nebo v některé z jejích podsložek.  

## <a name="create-a-c-project-using-vs-code"></a>Vytvoření C# projektu pomocí vs Code

1. Požadavky

    * [Vývojová sada pro](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code) všechna tato prostředí pro vs Code

1. Vytvořit nový projekt:

    * Přejít na **zobrazení** -> **paleta příkazů**
    * Vyberte **Q #: vytvořit nový projekt.**
    * Přejděte do umístění v systému souborů, kde chcete vytvořit aplikaci.
    * Po vytvoření projektu klikněte na tlačítko **Otevřít nový projekt...**

1. Spusťte aplikaci:

    * Přejít na **ladění** -> **Spustit bez ladění**
    * V okně výstup byste měli vidět následující text `Hello quantum world!`

Nyní můžete pokračovat ve vývoji ve vaší práci pomocí Visual Studio Code.

> [!NOTE]
> * Rozšíření Visual Studio Code v současné době nepodporuje pracovní prostory s více kořenovými složkami. Pokud máte více projektů v rámci jednoho VS Code pracovního prostoru, musí být všechny projekty obsaženy v rámci stejné kořenové složky.

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>Vytvoření C# projektu pomocí `dotnet` nástroje příkazového řádku

1. Požadavky

    * [Sada pro vývoj pro](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool) všechna ta na příkazovém řádku

1. Vytvoření nové aplikace

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. Přejít do nového adresáře aplikace

    ```bash
    cd <project name>
    ```

    Měli byste vidět, že byly vytvořeny dva soubory společně se soubory projektu aplikace: soubor Q # (`Operation.qs`) a soubor C# hostitele (`Driver.cs`).

1. Spuštění aplikace

    ```bash
    dotnet run
    ```

    Měl by se zobrazit následující výstup: `Hello quantum world!`

Teď budete pokračovat ve vývoji ve vaší práci pomocí nástrojů příkazového řádku.

## <a name="whats-next"></a>A co dál?

Teď, když jste vytvořili projekt v upřednostňovaném prostředí, můžete pokračovat ve vývoji vašeho vlastního navýšení.
