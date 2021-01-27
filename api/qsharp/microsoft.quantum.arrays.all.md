---
uid: Microsoft.Quantum.Arrays.All
title: All – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 17e61ea161b90fe089b7df7c10188d604d72dcfa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842898"
---
# <a name="all-function"></a>All – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Předané pole a predikát, který je definován pro prvky pole a kontroluje, zda všechny prvky pole odpovídají predikátu.

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Vstup

### <a name="predicate--t---bool"></a>predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funkce z `'T` `Bool` , která se používá ke kontrole prvků.


### <a name="array--t"></a>Array: t []

Pole prvků nad `'T` .



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`Bool`Hodnota funkce a predikátu použité pro všechny elementy.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ `array` prvků.

## <a name="example"></a>Příklad

Následující kód kontroluje, zda jsou všechny prvky pole nenulové:

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function AllDemo() : Unit {
    let predicate = NotEqualI(_, 0);
    let isNonZero = All(predicate, [2, 3, 4, 5, 6, 0]);
    Message($"{isNonZero}");
}
```

## <a name="remarks"></a>Poznámky

Funkce je definována pro obecné typy, tj., kdykoli máme pole `'T[]` a funkci, `predicate: 'T -> Bool` můžeme vytvořit `Bool` hodnotu, která označuje, zda všechny prvky vyhoví `predicate` .