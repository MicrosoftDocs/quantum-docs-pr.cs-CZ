---
title: Vývoj s aplikacemi v Q#
description: Naučte se vytvářet aplikace Q#, které se spouští z příkazového řádku.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 68f530d80e5c5f40dc2bcbb185879c3cb6f93f91
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834410"
---
# <a name="develop-with-no-locq-applications"></a>Vývoj s aplikacemi v Q#

Postupujte podle pokynů na kartě odpovídající vašemu prostředí.

Programy v Q# se dají spouštět samostatně, bez ovladače v hostitelském jazyce jako C#, F# nebo Python.

## <a name="prerequisites"></a>Požadavky

- [.NET Core SDK 3.1 nebo novější](https://www.microsoft.com/net/download)

## <a name="installation"></a>Instalace

I když můžete aplikaci v Q# sestavit v jakémkoli integrovaném vývojovém prostředí, doporučujeme použít Visual Studio Code (VS Code) nebo Visual Studio IDE nebo vyvíjet aplikace v Q# místně. Pro vývoj v cloudu prostřednictvím webového prohlížeče doporučujeme Visual Studio Codespaces. Vývoj v těchto prostředích poskytuje bohaté funkce rozšíření QDK, mezi které patří upozornění, zvýrazňování syntaxe, šablony projektů a další. 

Konfigurace VS Code:

1. Stáhněte si a nainstalujte [VS Code](https://code.visualstudio.com/download) (Windows, Linux a Mac).
2. Nainstalujte [Microsoft QDK pro VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Konfigurace sady Visual Studio:

1. Stáhněte si a nainstalujte [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 nebo novější s podporou multiplatformního vývoje .NET Core.
2. Stáhněte si a nainstalujte [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).

Konfigurace Visual Studio Codespaces:

1. Vytvořte [účet Azure](https://azure.microsoft.com/free/).
2. Vytvořte prostředí Codespaces. Postupujte podle [průvodce rychlým zprovozněním](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser). Při vytváření Codespace doporučujeme do pole úložiště Git zadat `microsoft/Quantum` a načíst nastavení specifická pro QDK.
3. Teď můžete nové prostředí spustit a začít vyvíjet v prohlížeči prostřednictvím [cloudového integrovaného vývojového prostředí VS Codespaces](https://online.visualstudio.com/environments). Další možností je využít místní instalaci editoru VS Code a použít Codespaces jako [vzdálené prostředí](https://docs.microsoft.com/visualstudio/online/how-to/vscode).


Pokud chcete nainstalovat QDK pro jiné prostředí, zadejte na příkazovém řádku následující:

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a>Vývoj s využitím Q#

Postupujte podle pokynů na kartě odpovídající vašemu prostředí.

### <a name="vs-code"></a>[VS Code](#tab/tabid-vscode)

Vytvoření nového projektu:

1. Klikněte na **Zobrazení** -> **Paleta příkazů** a vyberte **Q#: Vytvořit nový projekt**.
2. Klikněte na **Samostatná konzolová aplikace**.
3. Přejděte do umístění, kam chcete projekt uložit, a klikněte na **Vytvořit projekt**.
4. Po úspěšném vytvoření projektu klikněte na **Otevřít nový projekt...** v pravém dolním rohu.

Prozkoumejte projekt. Měl by se zobrazit zdrojový soubor s názvem `Program.qs`, což je program v Q#, který definuje jednoduchou operaci pro tisk zprávy na konzolu.

Spusťte aplikaci:

1. Klikněte na **Terminál** -> **Nový Terminál**.
2. Na příkazovém řádku terminálu zadejte `dotnet run`.
3. V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`

> [!NOTE]
> Rozšíření Q# pro VS Code aktuálně nepodporuje pracovní prostory s více kořenovými složkami. Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.

### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs)

Ověřte instalaci sady Visual Studio vytvořením aplikace Q# `Hello World`.

Vytvoření nové aplikace v Q#:

1. Otevřete Visual Studio a klikněte na **Soubor** -> **Nový** -> **Projekt**.
2. Do vyhledávacího pole zadejte `Q#`, vyberte **Aplikace vQ#** a klikněte na **Další**.
3. Zadejte název a umístění vaší aplikace a klikněte na **Vytvořit**.


Prozkoumejte projekt. Měl by se zobrazit zdrojový soubor s názvem `Program.qs`, což je program v Q#, který definuje jednoduchou operaci pro tisk zprávy na konzolu.

Spusťte aplikaci:

1. Vyberte **Ladit** -> **Spustit bez ladění**.
2. V okně konzoly by se měl zobrazit text `Hello quantum world!`.

> [!NOTE]
> Pokud máte v jednom řešení sady Visual Studio více projektů, všechny projekty obsažené v řešení se musí nacházet ve stejné složce jako řešení nebo v jedné z jejích podsložek.  

### <a name="other-editors-with-the-command-prompt"></a>[Další editory s příkazovým řádkem](#tab/tabid-cmdline)

Ověřte instalaci vytvořením aplikace Q# `Hello World`

1. Nainstalujte šablony projektů.

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. Vytvoření nové aplikace:

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. Přejděte do adresáře aplikace:

    ```dotnetcli
    cd runSayHello
    ```

    Tento adresář by měl nyní obsahovat soubor s názvem `Program.qs`, což je program v Q#, který definuje jednoduchou operaci pro tisk zprávy na konzolu. Tuto šablonu můžete upravit pomocí textového editoru a přepsat ji vlastními kvantovými aplikacemi. 

1. Spusťte program:

    ```dotnetcli
    dotnet run
    ```

1. Měl by se vypsat následující text: `Hello quantum world!`

***

## <a name="next-steps"></a>Další kroky

Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).
