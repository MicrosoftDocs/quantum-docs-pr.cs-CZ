---
title: Vývoj s aplikacemi v Q# v integrovaném vývojovém prostředí
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
ms.openlocfilehash: eeb567dedc1b8123b32faf7ed3a42bb51f16a7d2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228725"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a>Vývoj s aplikacemi v Q# v integrovaném vývojovém prostředí

Programy v Q# se dají spouštět samostatně, bez ovladače v hostitelském jazyce jako C#, F# nebo Python. K vývoji aplikací v Q# můžete použít Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces nebo libovolný jiný editor/IDE a spouštět aplikace z konzoly .NET. 

## <a name="prerequisites-for-all-environments"></a>Požadavky pro všechna prostředí

- [.NET Core SDK 3.1 nebo novější](https://www.microsoft.com/net/download)

## <a name="installation"></a>Instalace

I když můžete aplikaci v Q# sestavit v jakémkoli integrovaném vývojovém prostředí, doporučujeme použít Visual Studio Code (VS Code) nebo Visual Studio IDE nebo vyvíjet aplikace v Q# místně. Pro vývoj v cloudu prostřednictvím webového prohlížeče doporučujeme Visual Studio Codespaces. Vývoj v těchto prostředích využívá bohaté funkce rozšíření QDK, mezi které patří upozornění, zvýrazňování syntaxe, šablony projektů a další. 

### <a name="to-configure-for-vs-code"></a>Konfigurace pro VS Code:

1. Stáhněte si a nainstalujte [VS Code](https://code.visualstudio.com/download) (Windows, Linux a Mac).
2. Nainstalujte [Microsoft QDK pro VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

### <a name="to-configure-for-visual-studio"></a>Konfigurace pro Visual Studio:

1. Stáhněte si a nainstalujte [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 nebo novější s podporou multiplatformního vývoje .NET Core.
2. Stáhněte si a nainstalujte [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).

### <a name="to-configure-for-another-environment"></a>Konfigurace pro jiné prostředí: 

1. Na příkazovém řádku zadejte následující:

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a>Konfigurace pro Visual Studio Codespaces:

1. Vytvořte [účet Azure](https://azure.microsoft.com/free/).
2. Vytvořte prostředí Codespaces. Postupujte podle [průvodce rychlým zprovozněním](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser). Při vytváření Codespace doporučujeme do pole úložiště Git zadat `microsoft/Quantum` a načíst nastavení specifická pro QDK.
3. Teď můžete nové prostředí spustit a začít vyvíjet v prohlížeči prostřednictvím [cloudového integrovaného vývojového prostředí VS Codespaces](https://online.visualstudio.com/environments). Další možností je využít místní instalaci editoru VS Code a použít Codespaces jako [vzdálené prostředí](https://docs.microsoft.com/visualstudio/online/how-to/vscode).

## <a name="develop-with-no-locq"></a>Vývoj s využitím Q#

Postupujte podle pokynů na kartě odpovídající vašemu vývojovému prostředí.

### <a name="vs-code"></a>[VS Code](#tab/tabid-vscode)

Vytvoření nového projektu:

1. Klikněte na **Zobrazení** -> **Paleta příkazů** a vyberte **Q#: Vytvořit nový projekt**.
2. Klikněte na **Samostatná konzolová aplikace**.
3. Přejděte do umístění, kam chcete projekt uložit. Zadejte název projektu a klikněte na **Vytvořit projekt**.
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
