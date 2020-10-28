---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706168"
---
# <a name="columnat-function"></a>ColumnAt – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


Extrahuje sloupec z matice.

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Popis

Tato funkce extrahuje sloupec v matici v pořadí podle řádků.
Extrahování řádku corrsponds k přístupu k prvku prvního indexu, a proto nevyžaduje žádné další zpracování.

## <a name="input"></a>Vstup

### <a name="column--int"></a>sloupec: [int](xref:microsoft.quantum.lang-ref.int)

Sloupec matice


### <a name="matrix--t"></a>matice: t [] []

dvojrozměrné matice v pořadí podle řádků



## <a name="output--t"></a>Výstup: t []



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ každého prvku `matrix` .

## <a name="see-also"></a>Viz také

- [Microsoft. prohození. Arrays. prohození](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft. Forms. Arrays. diagonální](xref:Microsoft.Quantum.Arrays.Diagonal)