---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Prokládaný funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705960"
---
# <a name="interleaved-function"></a>Prokládaný funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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