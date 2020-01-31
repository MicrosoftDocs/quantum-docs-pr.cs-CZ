---
title: 'Vývoj pomocí Q # + Pythonu'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1e40c2dddeaf4fad41693c976493f10fffffa139
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76830997"
---
# <a name="develop-with-q--python"></a>Vývoj pomocí Q # + Pythonu

Nainstalujte QDK pro vývoj hostitelských programů v Pythonu, aby se volaly operace Q #.

1. Požadavky

    - [Python](https://www.python.org/downloads/) 3.6 nebo novější
    - Správce balíčků Pythonu [PIP](https://pip.pypa.io/en/stable/installing)
    - [.NET Core SDK 3,1 nebo novější](https://www.microsoft.com/net/download)


1. Nainstalujte balíček `qsharp`, balíček Pythonu, který umožňuje spolupráci mezi Q # a Pythonem.

    ```bash
    pip install qsharp
    ```

1. Nainstalujte `iqsharp`, jádro používané v Jupyter a Pythonu, které poskytuje základní funkce pro kompilaci a provádění operací Q #.

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. I když v jakémkoli integrovaném vývojovém prostředí můžete použít Q # s Pythonem, důrazně doporučujeme pro vaše aplikace pro Q # + Python používat rozhraní IDE Visual Studio Code (VS Code). Pomocí Visual Studio Code a rozšíření QDK Visual Studio Code získáte přístup k rozsáhlejším funkcím.

    - Nainstalovat [vs Code](https://code.visualstudio.com/download) (Windows, Linux a Mac)
    - Nainstalujte [rozšíření QDK pro vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

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

        ```bash
        python hello_world.py
        ```

    - Ověřte výstup. Výstupem programu by měly být následující řádky:

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * Pomocí poznámkových bloků Python Jupyter můžete také napsat klasický program v Pythonu a v buňkách volat operace Q #. Kód Pythonu je pouze běžný program v Pythonu.

## <a name="whats-next"></a>A co dál?

Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.write-program).
