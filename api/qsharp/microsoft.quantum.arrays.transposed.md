---
uid: Microsoft.Quantum.Arrays.Transposed
title: Funkce převzata
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705737"
---
# <a name="transposed-function"></a>Funkce převzata

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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