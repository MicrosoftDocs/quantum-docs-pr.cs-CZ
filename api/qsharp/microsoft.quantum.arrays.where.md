---
uid: Microsoft.Quantum.Arrays.Where
title: WHERE – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 97598aa25d2d085aaab94f3d60ee64db9e2b89d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219919"
---
# <a name="where-function"></a>WHERE – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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