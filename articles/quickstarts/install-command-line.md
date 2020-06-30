---
title: Vývoj aplikací příkazového řádku v Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274064"
---
# <a name="develop-with-q-command-line-applications"></a>Vývoj aplikací příkazového řádku v Q#

Programy Q# se dají spouštět samostatně, bez ovladače v hostitelském jazyce jako C#, F# nebo Python.

## <a name="prerequisites"></a>Požadavky

- [.NET Core SDK 3.1 nebo novější](https://www.microsoft.com/net/download)

## <a name="installation"></a>Instalace

I když můžete aplikaci příkazového řádku Q# sestavit v jakémkoli integrovaném vývojovém prostředí, doporučujeme použít Visual Studio Code (VS Code) nebo Visual Studio IDE. Vývoj v těchto nástrojích poskytuje přístup k bohaté paletě funkcí.

Konfigurace VS Code:

1. Stáhněte si a nainstalujte [VS Code](https://code.visualstudio.com/download) (Windows, Linux a Mac).
2. Nainstalujte [Microsoft QDK pro VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Konfigurace sady Visual Studio:

1. Stáhněte si a nainstalujte [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 nebo novější s podporou multiplatformního vývoje .NET Core.
2. Stáhněte si a nainstalujte [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).


## <a name="develop-with-q-using-vs-code"></a>Vývoj v jazyce Q# s využitím VS Code

Nainstalujte šablony projektů Q#:

1. Otevřete VS Code.
2. Klikněte na **Zobrazit** -> **Paleta příkazů**.
3. Vyberte **Q#: Instalovat šablony projektů**.

Když se zobrazí zpráva **Šablony projektů byly úspěšně nainstalovány**, sada QDK je připravena na vývoj vašich vlastních knihoven a aplikací.

Vytvoření nového projektu:

1. Klikněte na **Zobrazení** -> **Paleta příkazů** a vyberte **Q#: Vytvořit nový projekt**.
2. Klikněte na **Samostatná konzolová aplikace**.
3. Přejděte do umístění, kam chcete projekt uložit, a klikněte na **Vytvořit projekt**.
4. Po úspěšném vytvoření projektu klikněte na **Otevřít nový projekt...** v pravém dolním rohu.
        
Prozkoumejte projekt. Měl by se zobrazit zdrojový soubor s názvem `Program.qs`, což je program Q#, který definuje jednoduchou operaci pro tisk zprávy na konzolu.

Spusťte aplikaci:
1. Klikněte na **Terminál** -> **Nový Terminál**.
2. Na příkazovém řádku terminálu zadejte `dotnet run`.
3. V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`


> [!NOTE]
> Rozšíření Q# pro VS Code aktuálně nepodporuje pracovní prostory s více kořenovými složkami. Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.

## <a name="develop-with-q-using-visual-studio"></a>Vývoj v Q# v sadě Visual Studio

Ověřte instalaci sady Visual Studio vytvořením aplikace `Hello World` v jazyce Q#.

Vytvoření nové aplikace v jazyce Q#:
1. Otevřete Visual Studio a klikněte na **Soubor** -> **Nový** -> **Projekt**.
2. Do vyhledávacího pole zadejte `Q#`, vyberte **Aplikace Q#** a klikněte na **Další**.
3. Zadejte název a umístění vaší aplikace a klikněte na **Vytvořit**.


Prozkoumejte projekt. Měl by se zobrazit zdrojový soubor s názvem `Program.qs`, což je program Q#, který definuje jednoduchou operaci pro tisk zprávy na konzolu.

Spusťte aplikaci:
1. Vyberte **Ladit** -> **Spustit bez ladění**.
2. V okně konzoly by se měl zobrazit text `Hello quantum world!`.

> [!NOTE]
> Pokud máte v jednom řešení sady Visual Studio více projektů, všechny projekty obsažené v řešení se musí nacházet ve stejné složce jako řešení nebo v jedné z jejích podsložek.  


## <a name="next-steps"></a>Další kroky

Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).
