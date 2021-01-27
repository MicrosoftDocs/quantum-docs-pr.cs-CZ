---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840500"
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

## <a name="example"></a>Příklad

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```