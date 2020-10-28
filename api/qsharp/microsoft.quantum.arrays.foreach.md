---
uid: Microsoft.Quantum.Arrays.ForEach
title: Operace ForEach
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: ab6ac6eb913095f31ba166ac27f034f2e2875acf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706000"
---
# <a name="foreach-operation"></a>Operace ForEach

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


Předané pole a operace, která je definována pro prvky pole, vrátí nové pole, které se skládá z obrázků původního pole v rámci operace.

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Vstup

### <a name="action--t--u"></a>Action: t => ' U 

Operace z `'T` na `'U` , která je použita na každý prvek.


### <a name="array--t"></a>Array: t []

Pole prvků nad `'T` .



## <a name="output--u"></a>Výstup: U []

Pole `'U[]` prvků, které jsou mapovány `action` operací.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ `array` prvků.
### <a name="u"></a>U

Typ výsledku `action` operace.

## <a name="remarks"></a>Poznámky

Operace je definována pro obecné typy, tj. kdykoli máme pole `'T[]` a operaci, `action : 'T -> 'U` můžeme namapovat prvky pole a vytvořit nové pole typu `'U[]` .