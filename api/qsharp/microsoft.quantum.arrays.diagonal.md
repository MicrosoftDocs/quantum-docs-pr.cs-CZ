---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Funkce diagonálního
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706120"
---
# <a name="diagonal-function"></a>Funkce diagonálního

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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

## <a name="see-also"></a>Viz také

- [Microsoft. prohození. Arrays. prohození](xref:Microsoft.Quantum.Arrays.Transposed)