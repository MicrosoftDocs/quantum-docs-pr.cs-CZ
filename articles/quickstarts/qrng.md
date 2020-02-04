---
title: Vytvoření kvantového generátoru náhodných čísel
description: Vytvořte projekt v jazyku Q#, který ilustruje základní kvantové koncepce, jako je například superpozice, vytvořením kvantového generátoru náhodných čísel.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 134617455b720cc755b9ee9fb68fb59e624d3f1a
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820900"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>Rychlý start: Implementace kvantového generátoru náhodných čísel v jazyku Q#
Jednoduchým příkladem kvantového algoritmu implementovaného v jazyku Q# je kvantový generátor náhodných čísel. Tento algoritmus využívá charakter kvantové mechaniky a vytváří náhodné číslo. 

## <a name="prerequisites"></a>Požadavky

- Sada Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Vytvořte projekt v jazyku Q#](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>Napište operaci Q#

### <a name="q-operation-code"></a>Kód operace Q#

1. Obsah souboru Operation.qs nahraďte následujícím kódem:

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(qubit = Qubit())  { // Allocate a qubit.
                H(qubit);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(v);     // Measure the qubit value.
                Reset(qubit);
                return r;
            }
        }
    }
    ```

Jak je uvedeno v článku [Co jsou kvantové výpočty?](xref:microsoft.quantum.overview.what), qubit je jednotka kvantových informací, které můžou být v superpozici. Při změření může mít qubit jenom hodnotu 0 nebo 1. Během zpracování však stav qubitu představuje pravděpodobnost přečtení hodnoty 0 anebo 1 při měření. Tento pravděpodobnostní stav se nazývá superpozice. Na základě této pravděpodobnosti můžeme generovat náhodná čísla.

V rámci operace v jazyku Q # zavádíme datový typ `Qubit`, který je pro jazyk Q# nativní. Typ `Qubit` je možné přidělit jen pomocí příkazu `using`. Qubit je po přidělení vždycky ve stavu `Zero`. 

Pomocí operace `H` můžeme `Qubit` převést do superpozice. Ke změření qubitu a přečtení jeho hodnoty použijte vnitřní operaci `M`.

Když `Qubit` převedeme do superpozice a změříme ho, bude výsledkem při každém vyvolání kódu jiná hodnota. 

Když je pro `Qubit` zrušeno přidělení, musí pro něj být znovu nastaven stav `Zero`, jinak simulátor ohlásí běhovou chybu. Snadný způsob, jak toho dosáhnout, je vyvolat operaci `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Vizualizace kódu pomocí Blochovy koule

Severní pól na Blochově kouli představuje klasickou hodnotu **0** a jižní pól představuje klasickou hodnotu **1**. Každá superpozice může být reprezentována bodem na kouli (reprezentovaný šipkou). Čím blíž je konec šipky k pólu, tím vyšší je pravděpodobnost, že se qubit při změření převede na klasickou hodnotu přiřazenou k příslušnému pólu. Příklad: Stav qubitu reprezentovaného červenou šipkou na obrázku níže má vyšší pravděpodobnost, že při změření bude mít hodnotu **0**.

<img src="~/media/qrng-Bloch.png" width="175">

Tuto reprezentaci můžeme použít k vizualizaci toho, co kód dělá:

* Nejdřív začneme s qubitem inicializovaným ve stavu **0** a pomocí funkce `H` vytvoříme superpozici, ve které jsou pravděpodobnosti hodnot **0** a **1** stejné.

<img src="~/media/qrng-H.png" width="450">

* Pak qubit změříme a výstup uložíme:

<img src="~/media/qrng-meas.png" width="450">

Jelikož je výsledek měření zcela náhodný, získali jsme náhodný bit. Pokud chceme generovat celá čísla, můžeme tuto operaci volat vícekrát. Pokud například budeme tuto operaci volat třikrát a získáme tři náhodné bity, můžeme generovat náhodná 3-bitová čísla (tedy náhodné číslo v rozsahu 0 až 7).

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a>Vytvoření kompletního generátoru náhodných čísel s využitím hostitelského programu

Teď když máme operaci Q#, která generuje náhodné bity, můžeme ji použít k sestavení kompletního generátoru náhodných čísel s využitím hostitelského programu.

 ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[Python s Visual Studio Code nebo příkazovým řádkem](#tab/tabid-python)
 
 Pokud chcete nový program v jazyku Q# spustit z Pythonu, uložte jako soubor `host.py` tento kód:
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 Pak můžete hostitelský program Pythonu spustit z příkazového řádku:
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[C# s Visual Studio Code nebo příkazovým řádkem](#tab/tabid-csharp)
 
 Pokud chcete nový program v jazyku Q# spustit z C#, upravte soubor `Driver.cs` tak, aby obsahoval tento kód C#:
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 Pak můžete hostitelský program C# spustit z příkazového řádku:
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[C# s Visual Studiem 2019](#tab/tabid-vs2019)

 Pokud chcete nový program v jazyku Q# spustit z C# v sadě Visual Studio, upravte soubor `Driver.cs` tak, aby obsahoval tento kód C#:

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 Pak stiskněte klávesu F5, program se spustí a automaticky se zobrazí nové okno s vygenerovaným náhodným číslem: 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
