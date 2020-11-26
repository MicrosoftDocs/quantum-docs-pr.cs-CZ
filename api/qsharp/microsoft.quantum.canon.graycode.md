---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206880"
---
# <a name="graycode-function"></a>GrayCode – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vytvoří šedé sekvence kódu.

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>Vstup

### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

Počet bitů



## <a name="output--intint"></a>Výstup: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Pole řazených kolekcí členů. První hodnota v řazené kolekci členů je hodnota v GrayCode pořadí sekundová hodnota v řazené kolekci členů je pozice pro změnu v aktuální hodnotě, která se získá jako další.