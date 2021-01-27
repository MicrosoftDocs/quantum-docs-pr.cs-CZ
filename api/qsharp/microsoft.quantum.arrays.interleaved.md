---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Prokládaný funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848118"
---
# <a name="interleaved-function"></a>Prokládaný funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ponechá dvě pole (téměř) stejné velikosti.

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a>Popis

Tato funkce vrací prokládání dvou polí počínaje prvním prvkem z prvního pole, poté prvním prvkem z druhého pole a tak dále.

První pole musí být buď stejné délky jako druhá, nebo může mít jeden další prvek.

## <a name="input"></a>Vstup

### <a name="first--t"></a>First: t []

První pole, které má být prokládaný.


### <a name="second--t"></a>sekundy: t []

Druhé pole, které se má pronechávat.



## <a name="output--t"></a>Výstup: t []

Prokládané pole

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ každého prvku `first` a `second` .

## <a name="example"></a>Příklad

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```