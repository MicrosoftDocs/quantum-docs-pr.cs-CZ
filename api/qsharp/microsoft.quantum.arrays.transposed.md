---
uid: Microsoft.Quantum.Arrays.Transposed
title: Funkce převzata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850939"
---
# <a name="transposed-function"></a>Funkce převzata

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí transpozice matice reprezentované jako pole polí.

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a>Popis

Vstup jako $r \times c $ Matrix s $r $ Rows a $c $ Columns.  Matice je založena na řádcích, tj. `matrix[i][j]` přistupuje k elementu na řádku $i $ a sloupci $j $.

Tato funkce vrací matici $c \times r $, která je transpozice vstupní matice.

## <a name="input"></a>Vstup

### <a name="matrix--t"></a>matice: t [] []

Matice $r \times založené na řádku jazyka c $



## <a name="output--t"></a>Výstup: t [] []

$C \times r $ Matrix pro přeměňování

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ každého prvku `matrix` .

## <a name="example"></a>Příklad

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```