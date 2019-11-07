---
title: Vytvoření kvantového generátoru náhodných čísel
description: Vytvořte projekt v jazyku Q#, který ilustruje základní kvantové koncepce, jako je například superpozice, vytvořením kvantového generátoru náhodných čísel.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: c3039b92c4b3235a397d5cf31280ac2673706e9d
ms.sourcegitcommit: 2ca4755d1a63431e3cb2d2918a10ad477ec2e368
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462835"
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
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
                return r;
            }
        }
    }
    ```

Jak je uvedeno v článku [Co jsou kvantové výpočty?](xref:microsoft.quantum.overview.what), qubit je jednotka kvantových informací, které můžou být v superpozici. Při změření může mít qubit jenom hodnotu 0 nebo 1. Během zpracování však stav qubitu představuje pravděpodobnost přečtení hodnoty 0 anebo 1 při měření. Tento pravděpodobnostní stav se nazývá superpozice. Na základě této pravděpodobnosti můžeme generovat náhodná čísla.

V rámci operace v jazyku Q # zavádíme datový typ `Qubit`, který je pro jazyk Q# nativní. Typ `Qubit` je možné přidělit jen pomocí příkazu `using`. Qubit je po přidělení vždy ve stavu `Zero`. 

Pomocí operace `H` můžeme `Qubit` převést do superpozice. Ke změření qubitu a přečtení jeho hodnoty použijte vnitřní operaci `M`.

Když `Qubit` převedeme do superpozice a změříme ho, bude výsledkem při každém vyvolání kódu jiná hodnota. 

Když je pro `Qubit` zrušeno přidělení, musí pro něj být znovu nastaven stav `Zero`, jinak simulátor ohlásí běhovou chybu. Snadný způsob, jak toho dosáhnout, je vyvolat operaci `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Vizualizace kódu pomocí Blochovy koule

Na Blochově kouli představuje severní pól klasickou hodnotu **0** a jižní pól představuje klasickou hodnotu **1**. Každá superpozice může být reprezentována bodem na kouli (reprezentovaný šipkou). Čím blíž je konec šipky k pólu, tím vyšší je pravděpodobnost, že se qubit při změření převede na klasickou hodnotu přiřazenou k příslušnému pólu. Příklad: Stav qubitu reprezentovaného červenou šipkou na obrázku níže má vyšší pravděpodobnost, že při změření bude mít hodnotu **0**.

<img src="./Bloch.svg" width="175">

Tuto reprezentaci můžeme použít k vizualizaci toho, co kód dělá:

* Nejdřív začneme s qubitem inicializovaným ve stavu **0** a pomocí funkce `H` vytvoříme superpozici, ve které jsou pravděpodobnosti hodnot **0** a **1** stejné.

<img src="./H.svg" width="450">

* Pak qubit změříme a výstup uložíme:

<img src="./Measurement2.svg" width="450">

Jelikož je výsledek měření zcela náhodný, získali jsme náhodný bit. Pokud chceme generovat celá čísla, můžeme tuto operaci volat vícekrát. Pokud například budeme tuto operaci volat třikrát a získáme tři náhodné bity, můžeme generovat náhodná 3-bitová čísla (tedy náhodné číslo v rozsahu 0 až 7).
