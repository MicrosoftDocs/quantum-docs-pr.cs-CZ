---
title: 'Vývoj pomocí poznámkových bloků Q # Jupyter'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b7276f9b273f601f30e4938018398353b6a9102d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831065"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Vývoj pomocí poznámkových bloků Q # Jupyter

Nainstalujte QDK pro vývoj operací Q # v poznámkových blocích Q # Jupyter.

Jupyter poznámkové bloky umožňují místní provádění kódu společně s pokyny, poznámkami a dalšími obsahy. Toto prostředí je ideální pro psaní kódu Q # s vloženými vysvětleními nebo s využitím výpočetních interaktivních kurzů. Podívejte se, co všechno k vytváření vlastních poznámkových bloků v Q# potřebujete.

IQ# (anglicky se vyslovuje i-q-sharp) je rozšíření sady .NET Core SDK primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a simulaci operací v jazyce Q#.

> [!NOTE]
> * V poznámkových blocích Q # Jupyter můžete spustit pouze kód Q # a operace nelze volat z externích hostitelských programů (např. Python nebo C# Files). Toto prostředí není vhodné, pokud je vaším cílem kombinování externího programu klasického hostitele s programem.

1. Požadavky

    - [Python](https://www.python.org/downloads/) 3.6 nebo novější
    - [Poznámkový blok Jupyter](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3,1 nebo novější](https://www.microsoft.com/net/download)

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

    - Otevřete kopii poznámkového bloku Jupyter a vložte adresu URL poskytnutou příkazovým řádkem do prohlížeče.

    - Vytvořte poznámkový blok Jupyter s použitím jádra Q# a do první buňky poznámkového bloku přidejte následující kód:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Spusťte tuto buňku poznámkového bloku:

        ![Buňka poznámkového bloku Jupyter s využitím kódu Q#](~/media/install-guide-jupyter.png)

        Ve výstupu buňky by se měl zobrazit text `SayHello`. Při spouštění v poznámkových blocích Jupyter se kompiluje kód v jazyku Q# a výstupem poznámkového bloku jsou názvy nalezených operací.


    - V nové buňce spusťte právě vytvořenou operaci (v simulátoru) pomocí příkazu `%simulate`:

        ![Buňka poznámkového bloku Jupyter s využitím příkazu magic %simulate](~/media/install-guide-jupyter-simulate.png)

        Měla by se zobrazit zpráva vytištěná na obrazovce spolu s výsledkem operace, kterou jste vyvolali (tady vidíte prázdné řazené kolekce členů `()`, protože naše operace jednoduše vrátí `Unit` typ).

## <a name="whats-next"></a>A co dál?

Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.write-program).
