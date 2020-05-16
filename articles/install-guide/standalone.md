---
title: 'Vývoj s aplikacemi příkazového řádku Q #'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e829862521951c50cb42eebf261c803071a95275
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426437"
---
# <a name="develop-with-q-command-line-applications"></a>Vývoj s aplikacemi příkazového řádku Q #

Programy Q # se dají spouštět samostatně, bez ovladače v hostitelském jazyce, jako je C#, F # nebo Python.

## <a name="pre-requisites"></a>Požadavky

- [.NET Core SDK 3,1 nebo novější](https://www.microsoft.com/net/download)

## <a name="installation"></a>Instalace

I když můžete sestavit aplikace příkazového řádku Q # v jakémkoli integrovaném vývojovém prostředí, doporučujeme pro aplikace Q # použít Visual Studio Code (VS Code) nebo Visual Studio IDE. Vývoj v těchto nástrojích poskytuje přístup k bohatě funkčním funkcím.

Konfigurace VS Code:

1. Stáhněte a nainstalujte [vs Code](https://code.visualstudio.com/download) (Windows, Linux a Mac).
2. Nainstalujte [Microsoft QDK pro vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Konfigurace sady Visual Studio:

1. Stáhněte si a nainstalujte [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3 nebo novější s povolenou úlohou vývoje .NET Core pro různé platformy.
2. Stáhněte a nainstalujte [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).


## <a name="develop-with-q-using-vs-code"></a>Vývoj pomocí Q # pomocí VS Code

Instalace šablon projektů Q #:

1. Otevřete VS Code.
2. Klikněte na tlačítko **Zobrazit**  ->  **paletu příkazů**.
3. Vyberte **Q #: Instalace šablon projektů**.

Po **úspěšném dokončení instalace šablon projektů** je QDK připravený k použití s vlastními aplikacemi a knihovnami.

Vytvoření nového projektu:

1. Klikněte na **Zobrazit**  ->  **paletu příkazů** a vyberte **Q #: vytvořit nový projekt**.
2. Klikněte na **samostatná Konzolová aplikace**.
3. Přejděte do umístění, kam chcete projekt uložit, a klikněte na **vytvořit projekt**.
4. Po úspěšném vytvoření projektu klikněte v pravém dolním rohu na **Otevřít nový projekt...** .
        
Zkontrolujte projekt. Měl by se zobrazit zdrojový soubor s názvem `Program.qs` , což je program Q #, který definuje jednoduchou operaci pro tisk zprávy do konzoly.

Spusťte aplikaci:
1. Klikněte na **terminál**  ->  **nový terminál**.
2. Na příkazovém řádku terminálu zadejte `dotnet run` .
3. V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`


> [!NOTE]
> Pracovní prostory s více kořenovými složkami se v současné době rozšíření VS Code Q # nepodporují. Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.

## <a name="develop-with-q-using-visual-studio"></a>Vývoj pomocí Q # pomocí sady Visual Studio

Ověřte instalaci sady Visual Studio vytvořením aplikace Q # `Hello World` .

Vytvoření nové aplikace Q #:
1. Otevřete Visual Studio a klikněte na **soubor**  ->  **Nový**  ->  **projekt**.
2. `Q#`Do vyhledávacího pole zadejte, vyberte **Q # Application** a klikněte na **Další**.
3. Zadejte název a umístění vaší aplikace a klikněte na **vytvořit**.


Zkontrolujte projekt. Měl by se zobrazit zdrojový soubor s názvem `Program.qs` , což je program Q #, který definuje jednoduchou operaci pro tisk zprávy do konzoly.

Spusťte aplikaci:
1. Vyberte **ladit**  ->  **Spustit bez ladění**.
2. V okně konzoly by se měl zobrazit text `Hello quantum world!`.

> [!NOTE]
> Pokud máte více projektů v rámci jednoho řešení sady Visual Studio, všechny projekty, které jsou obsaženy v řešení, musí být ve stejné složce jako řešení nebo v jedné z jejích podsložek.  


## <a name="next-steps"></a>Další kroky

Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).
