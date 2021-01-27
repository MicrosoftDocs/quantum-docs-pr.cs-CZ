---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846255"
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

## <a name="example"></a>Příklad

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a>Viz také

- [Microsoft. prohození. Arrays. prohození](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft. Forms. Arrays. diagonální](xref:Microsoft.Quantum.Arrays.Diagonal)