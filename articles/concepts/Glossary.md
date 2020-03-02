---
title: Glosář pro výpočetní výkon
description: Glosář běžných podmínek, akcí a objektů používaných při práci.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: f47d87f5bc9d677baa12a7ac1581af72894e8a4b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909887"
---
# <a name="quantum-computing-glossary"></a>Glosář pro výpočetní výkon

|Období|Definice|
|-------------|----------|
|Sousednít|Složitá sdružená transpozice operace. Pro operace, které implementují operátor s jednou jednotkou, je sousední osoba inverzní k operaci.|
|Kompatibilní|Operace a funkce jsou souhrnně označovány jako *volatelné*.|
|Standard|Operace a funkce definované v Q # sestavují na Logic definované v předehru. Standardní implementace knihovny je nezávislá s ohledem na cílové počítače.|
|Skupina Clifford|Sada operací, které zabírají octants koule Bloch. Mezi ně patří: `X`, `Y`, `Z`, `H` a `S`|
|Kontrol|Operace s incidentem, která přijímá jednu nebo více qubits jako EnableRSS pro cílovou operaci.|
|Zápis Dirac|Zkrácený reprezentace stavu nestavení Další podrobnosti najdete v části [Dirac Notation](xref:microsoft.quantum.concepts.dirac) .|
|Eigenvalues a eigenvectors|Podrobnosti najdete v [části s pokročilou maticí](xref:microsoft.quantum.concepts.matrix-advanced) .|
|EPR pár|Označuje se také jako [stav zvonku](https://en.wikipedia.org/wiki/Bell_state) .|
|Vývoji|Jak se stav mění v čase. Příklad najdete v části v tématu <xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials>. |
|Funkce|Čistě klasické rutiny v jazyce Q #|
| <a id="global-phase"></a>Globální fáze | Dva stavy, které jsou identické až na násobek komplexního čísla $e ^ {i\phi} $, se říká, že se liší až do globální fáze. Na rozdíl od místních fází nelze globální fáze dodržet prostřednictvím žádné míry. Další podrobnosti najdete v tématu věnovaném [měřením Pauli](xref:microsoft.quantum.concepts.pauli) . |
|Měření|Získání klasického bitu z qubit (nebo sady qubits). Další podrobnosti najdete v části věnované [konceptům qubit](xref:microsoft.quantum.concepts.qubit) .|
|Měnitelné|Proměnná, jejíž hodnota může být po vytvoření změněna.|
|Obor názvů|Popisek pro kolekci souvisejících názvů (typicky operace, funkce a typy). Obor názvů například [`Microsoft.Quantum.Preparation`](xref:microsoft.quantum.preparation) popisky všech symbolů definovaných ve standardní knihovně, které vám pomůžou s přípravou počátečních stavů.|
|Operace|Základní jednotka provádění ve službě Q #. Zhruba odpovídá funkci v C, C++ nebo Pythonu, případně statické metodě v C# nebo Javě.|
|Aplikace operátora|Provádění operací s více operačními operacemi. To obvykle platí jednotnou matici s aktuálním vektorem stavu. Další podrobnosti najdete v tématu [Úvod do konceptů](xref:microsoft.quantum.concepts.intro) .|
|Oracle|Podprogram, který poskytuje informace závislé na datech pro algoritmus v době běhu. Cílem je obvykle poskytnout nadmnožinu výstupů odpovídajících vstupům, které jsou umístěny na pozici.   |
|Částečná aplikace|Volání funkce nebo operace bez všech požadovaných parametrů. Vrátí nový, který lze volat, který potřebuje pouze chybějící parametry, které byly zadány v budoucí aplikaci.|
|Pauli operátory|`X`, `Y` a `Z`.|
|Předehru|Sada primitivních a klasických operací a funkcí definovaných jednotlivými cílovými počítači místo na úrovni Q #.|
|Okruh|Reprezentace programu pro počítač s přísystémem na více počítačů. Další podrobnosti najdete v části <xref:microsoft.quantum.concepts.circuits>.|
|Stav pro stav|Reprezentace qubits v systému. To je obvykle označeno jako složitý vektor sloupce. Další informace naleznete v tématu <xref:microsoft.quantum.concepts.vectors>. |
|Qubit|Jednotka úložiště. Další podrobnosti najdete v části <xref:microsoft.quantum.concepts.qubit>.|
|Opakovat až do – úspěšné|Algoritmus pro všechna ta, který se probabilistically úspěšně. Po selhání rutina zopakuje pokus, dokud neproběhne úspěšně (nebo bylo dosaženo limitu). |
|Cílový počítač|Cíl kompilace, který snižuje abstraktní program pro plnění do hardwaru nebo simulace. To obvykle zahrnuje opakované zápisy pro mnoho účelů, včetně nahrazení brány, kódování pro korekci chyb, geometrické rozložení a další.|
|Řazené kolekce členů|Typy oddělené čárkami se seskupují společně prostřednictvím závorek. |
|Uživatelem definovaný typ|Kolekce předdefinovaných nebo dříve definovaných typů, které mohou být označovány jako jedna jednotka.|
