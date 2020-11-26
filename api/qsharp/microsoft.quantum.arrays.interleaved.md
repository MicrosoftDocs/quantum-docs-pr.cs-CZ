---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Prokládaný funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220956"
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