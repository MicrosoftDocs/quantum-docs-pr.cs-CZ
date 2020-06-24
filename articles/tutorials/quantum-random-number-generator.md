---
title: Vytvoření kvantového generátoru náhodných čísel
description: Vytvořte projekt v jazyku Q#, který ilustruje základní kvantové koncepce, jako je například superpozice, vytvořením kvantového generátoru náhodných čísel.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 18e8975e513a87c0a67a6dbb5586cc7dab5a93fb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274483"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>Kurz: Implementace kvantového generátoru náhodných čísel v jazyku Q\#

Jednoduchým příkladem kvantového algoritmu implementovaného v jazyku Q# je kvantový generátor náhodných čísel. Tento algoritmus využívá charakter kvantové mechaniky a vytváří náhodné číslo.

## <a name="prerequisites"></a>Požadavky

- Sada Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Vytvořte projekt v jazyce Q# buď [pomocí jazyka Q# z příkazového řádku](xref:microsoft.quantum.install.standalone), [pomocí hostitelského programu v Pythonu](xref:microsoft.quantum.install.python), nebo [pomocí hostitelského programu v jazyce C#](xref:microsoft.quantum.install.cs).

## <a name="write-a-q-operation"></a>Napište operaci Q#

### <a name="q-operation-code"></a>Kód operace Q#

1. Obsah souboru Program.qs nahraďte následujícím kódem:

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

Jak je uvedeno v článku [Principy kvantových výpočtů](xref:microsoft.quantum.overview.understanding), qubit je jednotka kvantových informací, která může být v superpozici různých stavů. Při změření může mít qubit jenom hodnotu 0 nebo 1. Během zpracování však stav qubitu představuje pravděpodobnost přečtení hodnoty 0 anebo 1 při měření. Tento pravděpodobnostní stav se nazývá superpozice. Na základě této pravděpodobnosti můžeme generovat náhodná čísla.

V rámci operace v jazyku Q # zavádíme datový typ `Qubit`, který je pro jazyk Q# nativní. Typ `Qubit` je možné přidělit jen pomocí příkazu `using`. Qubit je po přidělení vždycky ve stavu `Zero`. 

Pomocí operace `H` můžeme `Qubit` převést do superpozice. Ke změření qubitu a přečtení jeho hodnoty použijte vnitřní operaci `M`.

Když `Qubit` převedeme do superpozice a změříme ho, bude výsledkem při každém vyvolání kódu jiná hodnota.

Pokud `Qubit` je zrušeno přidělení, musí být explicitně nastaveno zpět na `Zero` stav, jinak simulátor ohlásí chybu za běhu. Snadný způsob, jak toho dosáhnout, je vyvolat operaci `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Vizualizace kódu pomocí Blochovy koule

Severní pól na Blochově kouli představuje klasickou hodnotu **0** a jižní pól představuje klasickou hodnotu **1**. Každá superpozice může být reprezentována bodem na kouli (reprezentovaný šipkou). Čím blíž je konec šipky k pólu, tím vyšší je pravděpodobnost, že se qubit při změření převede na klasickou hodnotu přiřazenou k příslušnému pólu. Příklad: Stav qubitu reprezentovaného červenou šipkou na obrázku níže má vyšší pravděpodobnost, že při změření bude mít hodnotu **0**.

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

Tuto reprezentaci můžeme použít k vizualizaci toho, co kód dělá:

* Nejdřív začneme s qubitem inicializovaným ve stavu **0** a pomocí funkce `H` vytvoříme superpozici, ve které jsou pravděpodobnosti hodnot **0** a **1** stejné.

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* Pak qubit změříme a výstup uložíme:

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

Jelikož je výsledek měření zcela náhodný, získali jsme náhodný bit. Pokud chceme generovat celá čísla, můžeme tuto operaci volat vícekrát. Pokud například budeme tuto operaci volat třikrát a získáme tři náhodné bity, můžeme generovat náhodná 3-bitová čísla (tedy náhodné číslo v rozsahu 0 až 7).


## <a name="creating-a-complete-random-number-generator"></a>Vytvoření kompletního generátoru náhodných čísel

Teď když máme operaci Q#, která generuje náhodné bity, můžeme ji použít k sestavení kompletního generátoru náhodných čísel. Můžeme použít aplikace příkazového řádku v Q # nebo hostitelský program.



### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[Aplikace příkazového řádku v Q# s využitím sady Visual Studio nebo editoru Visual Studio Code](#tab/tabid-qsharp)

Pokud chcete vytvořit kompletní aplikaci příkazového řádku v Q#, přidejte do programu v Q# následující vstupní bod: 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

Spustitelný soubor spustí operaci nebo funkci označenou atributem `@EntryPoint()` na simulátoru nebo v estimátoru prostředků, a to v závislosti na konfiguraci projektu a možnostech příkazového řádku.

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

V sadě Visual Studio se skript jednoduše spustí stisknutím Ctrl + F5.

V editoru VS Code při prvním použití sestavte Program.qs zadáním následujícího příkazu na terminálu:

```dotnetcli
dotnet build
```

Pro následná spuštění není potřeba ho sestavovat znovu. Pokud ho chcete spustit, zadejte následující příkaz a stiskněte Enter:

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python s Visual Studio Code nebo příkazovým řádkem](#tab/tabid-python)

Pokud chcete nový program v jazyku Q# spustit z Pythonu, uložte jako soubor `host.py` tento kód:

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

Pak můžete hostitelský program Pythonu spustit z příkazového řádku:

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[C# s využitím editoru Visual Studio Code nebo sady Visual Studio](#tab/tabid-csharp)

Pokud chcete nový program v jazyku Q# spustit z C#, upravte soubor `Driver.cs` tak, aby obsahoval tento kód C#:

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

Pak můžete hostitelský program v C# spustit z příkazového řádku (v sadě Visual Studio byste měli stisknout F5):

```bash
$ dotnet run
The random number generated is 42
```

***
