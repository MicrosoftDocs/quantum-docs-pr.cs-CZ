---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704168"
---
# <a name="graycode-function"></a>GrayCode – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vytvoří šedé sekvence kódu.

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>Vstup

### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

Počet bitů



## <a name="output--intint"></a>Výstup: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Pole řazených kolekcí členů. První hodnota v řazené kolekci členů je hodnota v GrayCode pořadí sekundová hodnota v řazené kolekci členů je pozice pro změnu v aktuální hodnotě, která se získá jako další.