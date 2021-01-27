---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Funkce diagonálního
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 2857046f59a958fed106af0944b75baaa3292e96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842830"
---
# <a name="diagonal-function"></a>Funkce diagonálního

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí pole diagonálních elementů dvojrozměrného pole.

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Popis

Pokud dvojrozměrné pole nemá čtvercový tvar, vrátí se hodnota příčně nad minimálním počtem řádků a sloupců.

## <a name="input"></a>Vstup

### <a name="matrix--t"></a>matice: t [] []

dvojrozměrné matice v pořadí podle řádků



## <a name="output--t"></a>Výstup: t []



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ každého prvku `matrix` .

## <a name="example"></a>Příklad

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let diagonal = Diagonal(matrix);
// same as: column = [1, 5, 9]
```

## <a name="see-also"></a>Viz také

- [Microsoft. prohození. Arrays. prohození](xref:Microsoft.Quantum.Arrays.Transposed)