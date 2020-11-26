---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210094"
---
# <a name="columnat-function"></a>ColumnAt – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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