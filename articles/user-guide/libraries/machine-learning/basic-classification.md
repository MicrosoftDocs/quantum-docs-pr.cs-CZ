---
title: Základní klasifikace s Machine Learningovou knihovnou
description: Naučte se spouštět sekvenční třídění na základě počtu počátečních a napsaných v Q# Machine Learning knihovně Microsoft QDK.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: f9c3e7ab85c0f0d1a6063e593607d35c5cb76936
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868963"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>Základní klasifikace: klasifikace dat pomocí QDK

V tomto rychlém startu se dozvíte, jak spustit sekvenční třídění na základě počtu počátečních a popsaných informací Q# pomocí Machine Learning knihovny QDK. 

V této příručce použijeme datovou sadu s poloviční měsíc pomocí struktury klasifikátoru definované v Q# .

## <a name="prerequisites"></a>Požadavky

- Sada Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Vytvořte Q# projekt pro [hostitelský program Pythonu](xref:microsoft.quantum.install.python) nebo pro [hostitelský program C#](xref:microsoft.quantum.install.cs).

## <a name="host-program"></a>Hostitelský program

Hostitelský program se skládá ze tří částí:

- Načtěte datovou sadu a vyberte sadu počátečních parametrů pro váš model.
- Spusťte školení a určete parametry a posun modelu.
- Ověří model a určí jeho přesnost.

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python s Visual Studio Code nebo příkazovým řádkem](#tab/tabid-python)

    Pokud chcete spustit Q# klasifikátor z Pythonu, uložte následující kód jako `host.py` . Nezapomeňte, že také potřebujete Q# soubor `Training.qs` , který je vysvětlen dále v tomto kurzu.

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    Pak můžete hostitelský program Pythonu spustit z příkazového řádku:

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# s Visual Studio Code nebo příkazovým řádkem](#tab/tabid-csharp)

    Chcete-li spustit Q# klasifikátor z C#, uložte následující kód jako `Host.cs` . Nezapomeňte, že také potřebujete Q# soubor `Training.qs` , který je vysvětlen dále v tomto kurzu.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Pak můžete hostitelský program C# spustit z příkazového řádku:

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[C# s Visual Studiem 2019](#tab/tabid-vs2019)

    Chcete-li spustit nový Q# program z c# v aplikaci Visual Studio, upravte `Host.cs` tak, aby obsahovalo následující kód jazyka c#. Nezapomeňte, že také potřebujete Q# soubor `Training.qs` , který je vysvětlen dále v tomto kurzu.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Pak stiskněte klávesu F5, program se spustí a automaticky se zobrazí nové okno s následujícími výsledky: 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>\#Kód třídění Q

Teď se podíváme, jak se operace vyvolané hostitelským programem definují v tématu Q# .
Následující kód ukládáme do souboru s názvem `Training.qs` .

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

Nejdůležitější funkce a operace definované v kódu výše jsou:

- `ClassifierStructure() : ControlledRotation[]`: v této funkci nastavíme strukturu modelu našeho okruhu přidáním vrstev řízených bran, které považujeme za. Tento krok je podobný deklaraci vrstev neurons v sekvenčním modelu hloubkového učení.
- `TrainHalfMoonModel() : (Double[], Double)`: Tato operace je základní částí kódu a definuje školení. Tady načteme ukázky z datové sady zahrnuté do knihovny, nastavíme parametry Hyper a počáteční parametry pro školení a my zahájíme školení voláním operace `TrainSequentialClassifier` zahrnuté do knihovny. Vytvoří výstup parametrů a posunu, který určuje klasifikátor.
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: Tato operace definuje proces ověření pro vyhodnocení modelu. Tady načteme ukázky pro ověřování, počet měření na vzorek a toleranci. Vyprodukuje počet chybných klasifikací na zvolené dávce vzorků pro ověření.

## <a name="next-steps"></a>Další kroky

Nejprve můžete přehrát kód a zkusit změnit některé parametry, abyste viděli, jak ovlivní školení. V dalším kurzu pak [Navrhněte vlastní třídění](xref:microsoft.quantum.libraries.machine-learning.design), kde se dozvíte, jak definovat strukturu třídění.
