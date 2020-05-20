---
title: Vývoj s využitím poznámkových bloků Jupyter v Q#
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 0c4dc856c94b0a694fb99607eda64cec4d5c221d
ms.sourcegitcommit: 328f45a0b64cb6b325fa9d3b3ddb74a6a7a97ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/19/2020
ms.locfileid: "83660772"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Vývoj s využitím poznámkových bloků Jupyter v Q#

Nainstalujte QDK pro vývoj operací Q # v poznámkových blocích Q # Jupyter.

Jupyter poznámkové bloky umožňují místní provádění kódu společně s pokyny, poznámkami a dalšími obsahy. Toto prostředí je ideální pro psaní kódu Q # s vloženými vysvětleními nebo s využitím výpočetních interaktivních kurzů. Podívejte se, co všechno k vytváření vlastních poznámkových bloků v Q# potřebujete.

IQ# (anglicky se vyslovuje i-q-sharp) je rozšíření sady .NET Core SDK primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a simulaci operací v jazyce Q#.

> [!NOTE]
> * V poznámkových blocích Q # Jupyter můžete spustit pouze kód Q # a operace nelze volat z externích hostitelských programů (například souborů Python nebo C#). Toto prostředí není vhodné, pokud je vaším cílem kombinování externího programu klasického hostitele s programem.

1. Požadavky

    - [Python](https://www.python.org/downloads/) 3.6 nebo novější
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

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

    - Chcete-li otevřít Jupyter Notebook, zkopírujte a vložte adresu URL poskytnutou příkazovým řádkem do prohlížeče.

    - Vytvořte Jupyter Notebook s jádrem Q # a přidejte do první buňky poznámkového bloku následující kód:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Spusťte tuto buňku poznámkového bloku:

        ![Jupyter Notebook buňka s kódem Q #](~/media/install-guide-jupyter.png)

        Ve výstupu buňky by se měl zobrazit text `SayHello`. Při spuštění v Jupyter Notebook se kód Q # zkompiluje a Poznámkový blok vytvoří název operací, které najde.


    - V nové buňce spusťte právě vytvořenou operaci (v simulátoru) pomocí `%simulate` příkazu:

        ![Jupyter Notebook buňka s% simulující Magic](~/media/install-guide-jupyter-simulate.png)

        Měla by se zobrazit zpráva vytištěná na obrazovce spolu s výsledkem operace, kterou jste vyvolali (tady vidíte prázdné řazené kolekce členů, `()` protože naše operace jednoduše vrací `Unit` typ).

## <a name="next-steps"></a>Další kroky

Teď, když jste nainstalovali QDK pro poznámkové bloky Q # Jupyter, můžete napsat a spustit [svůj první program](xref:microsoft.quantum.quickstarts.qrng) pro práci pomocí zápisu kódu Q # přímo v prostředí Jupyter notebook.

Další příklady toho, co můžete dělat s poznámkovým blokem Q # Jupyter, najdete na adrese:
- [Úvod do Q # a Jupyter notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Najdete tu Jupyter Notebook Q #, která ukazuje, jak v tomto prostředí použít Q #.
- Ve formě [Katasch](xref:microsoft.quantum.overview.katas)poznámkových bloků Q # Jupyter, což je open source kolekce kurzů s vlastním tempem a sady cvičení programování. Dobrým výchozím bodem je [katas Poznámkový blok](https://github.com/microsoft/QuantumKatas#tutorial-topics) pro počáteční hodnotu. Katasa za sebou se zaměřuje na výuku, které vám pomohou vymezit výpočetní výkon a programování Q # ve stejnou dobu. Jedná se o skvělý příklad toho, jaký druh obsahu můžete vytvořit pomocí poznámkových bloků Q # Jupyter.
