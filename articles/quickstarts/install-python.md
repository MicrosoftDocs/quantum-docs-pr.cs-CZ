---
title: Vývoj s využitím Q# a Pythonu
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274049"
---
# <a name="develop-with-q-and-python"></a>Vývoj s využitím Q# a Pythonu

Nainstalujte sadu QDK pro vývoj hostitelských programů v Pythonu, volajících operace v Q#.

1. Požadavky

    - [Python](https://www.python.org/downloads/) 3.6 nebo novější
    - Správce balíčků Pythonu [PIP](https://pip.pypa.io/en/stable/installing)
    - [Sada .NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Nainstalujte `qsharp` – balíček Pythonu, který umožňuje spolupráci mezi Q# a Pythonem.

    ```
    pip install qsharp
    ```

1. Nainstalujte IQ# – jádro primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a spouštění operací v jazyce Q#.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Pokud se během kroku `dotnet iqsharp install` zobrazí chyba, otevřete nové okno terminálu a zkuste to znovu.
    > Pokud to pořád nefunguje, zkuste najít nainstalovaný nástroj `dotnet-iqsharp` (ve Windows `dotnet-iqsharp.exe`) a spusťte:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > kde `/path/to/dotnet-iqsharp` nahraďte absolutní cestou k nástroji `dotnet-iqsharp` v systému souborů.
    > Obvykle bude ve složce `.dotnet/tools` ve vašem uživatelském profilu.
  
1. I když Q# s Pythonem můžete použít v jakémkoli integrovaném vývojovém prostředí, důrazně doporučujeme pro vaše aplikace Q# + Python používat rozhraní IDE Visual Studio Code (VS Code). Použitím sady Visual Studio Code a rozšíření QDK získáte přístup k rozsáhlejším funkcím.

    - Nainstalujte [VS Code](https://code.visualstudio.com/download) (Windows, Linux a Mac)
    - Nainstalujte [rozšíření QDK pro VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

1. Ověřte instalaci vytvořením aplikace `Hello World`.

    - Vytvořte minimální operaci v jazyku Q# tím, že vytvoříte soubor s názvem `Operation.qs` a do něj přidáte následující kód:

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
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

        ```
        python hello_world.py
        ```

    - Ověřte výstup. Výstupem programu by měly být následující řádky:

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * Pomocí poznámkových bloků Jupyter v Pythonu můžete také napsat klasický program v Pythonu a v buňkách volat operace Q#. Kód Pythonu je běžný program v Pythonu.

## <a name="next-steps"></a>Další kroky

Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).
