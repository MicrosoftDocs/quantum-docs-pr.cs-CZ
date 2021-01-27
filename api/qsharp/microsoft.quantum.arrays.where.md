---
uid: Microsoft.Quantum.Arrays.Where
title: WHERE – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 4a938114689177f7a9ee182e6e5f36debe4edac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842220"
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