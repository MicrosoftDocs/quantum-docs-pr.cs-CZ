---
title: 'Spustit programy Q # bez ovladače a jazyka hostitele'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706797"
---
# <a name="q-command-line-applications"></a>Aplikace příkazového řádku Q #

Programy Q # se dají spouštět samostatně, bez ovladače v hostitelském jazyce, jako je C#, F # nebo Python.

## <a name="pre-requisites"></a>Požadavky

- [.NET Core SDK 3,1 nebo novější](https://www.microsoft.com/net/download)

## <a name="installation"></a>Instalace

I když můžete sestavovat aplikace příkazového řádku Q # v jakémkoli integrovaném vývojovém prostředí, důrazně doporučujeme použít Visual Studio Code (VS Code) nebo Visual Studio IDE pro vaše aplikace Q #. Pomocí VS Code nebo Visual studia a rozšíření QDK Visual Studio Code získáte přístup k rozsáhlejším funkcím.

- Nainstalovat [vs Code](https://code.visualstudio.com/download) (Windows, Linux a Mac)
- Nainstalujte [rozšíření QDK pro vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) nebo
- [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 s povolenými úlohami vývoje pro různé platformy pomocí rozhraní .NET Core
- Stažení a instalace [rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)


## <a name="develop-with-q-using-vs-code"></a>Vývoj pomocí Q # pomocí VS Code

Nainstalujte šablony kvantového projektu:

- Přejít na **View** -> **paletu příkazů** zobrazení
- Vyberte **Q #: Instalace šablon projektů**

Teď máte sadu Quantum Development Kit nainstalovanou a připravenou k používání ve vašich vlastních aplikacích a knihovnách.
- Vytvořte nový projekt:
  - Přejít na **View** -> **paletu příkazů** zobrazení
  - Vyberte **Q #: vytvořit nový projekt.**
  - Vybrat **samostatnou konzolovou aplikaci**
  - Přejděte do umístění v systému souborů, ve kterém chcete aplikaci vytvořit.
  - Po vytvoření projektu klikněte na tlačítko **Otevřít nový projekt**.
        
- Prozkoumejte projekt.
  - Měl by se zobrazit, že soubor `Program.qs` nazvaný byl vytvořen, což je program Q #, který definuje jednoduchou operaci pro tisk zprávy do konzoly.

- Spusťte aplikaci:
  - Přejít na **terminál** -> **nový terminál**
  - Napište`dotnet run`
  - V okně s výstupem by se měl zobrazit tento text: `Hello quantum world!`


> [!NOTE]
> * Rozšíření Visual Studio Code aktuálně nepodporuje pracovní prostory s více kořenovými složkami. Pokud máte víc projektů v rámci jednoho pracovního prostoru VS Code, musí se všechny projekty nacházet ve stejné kořenové složce.

## <a name="develop-with-q-using-visual-studio"></a>Vývoj pomocí Q # pomocí sady Visual Studio

Ověřte instalaci vytvořením aplikace `Hello World`.

- Vytvořte novou aplikaci v jazyku Q#.
  - Přejít na **soubor** -> **Nový** -> **projekt**
  - Do vyhledávacího pole zadejte `Q#`.
  - Vyberte **Aplikace Q#**.
  - Vybrat **Další**
  - Vyberte název a umístění aplikace.
  - Vyberte **vytvořit** .

- Prozkoumejte projekt.
  - Měl by se zobrazit, že byl `Program.qs` vytvořen soubor s názvem, což je program Q #, který definuje jednoduchou operaci pro tisk zprávy do konzoly.

- Spuštění aplikace
  - Vyberte **ladit** -> **Spustit bez ladění**
  - V okně konzoly by se měl zobrazit text `Hello quantum world!`.

> [!NOTE]
> * Pokud řešení sady Visual Studio obsahuje více projektů, musí se všechny projekty obsažené v řešení nacházet ve stejné složce jako řešení nebo v jedné z jejích podsložek.  


## <a name="whats-next"></a>Co dále?

Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.write-program).
