---
uid: Microsoft.Quantum.Arrays.Where
title: WHERE – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 1c9fa0463ed49788d12502257d735b965565d1ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705697"
---
# <a name="where-function"></a>WHERE – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


V případě predikátu a pole vrátí indexy tohoto pole, kde má predikát hodnotu true.

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a>Vstup

### <a name="predicate--t---bool"></a>predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funkce z `'T` na logickou hodnotu, která slouží k filtrování prvků.


### <a name="array--t"></a>Array: t []

Pole prvků nad `'T` .



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]

Pole indexů, kde `predicate` je true.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ `array` prvků.