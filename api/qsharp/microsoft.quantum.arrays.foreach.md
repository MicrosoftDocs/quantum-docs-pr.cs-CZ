---
uid: Microsoft.Quantum.Arrays.ForEach
title: Operace ForEach
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: 90dd6f94408d37d2b32d82e772a482b0e69c523f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848589"
---
# <a name="foreach-operation"></a>Operace ForEach

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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