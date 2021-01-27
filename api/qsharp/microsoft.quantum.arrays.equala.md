---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equals – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848694"
---
# <a name="equala-function"></a>Equals – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zadaná dvě pole stejného typu a predikát, který je definován pro páry prvků pole, kontroluje, zda jsou pole shodná.

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a>Vstup

### <a name="equal--tt---bool"></a>EQUAL: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funkce z řazené kolekce členů se `('T, 'T)` `Bool` používá ke kontrole, zda jsou dva prvky pole stejné.


### <a name="array1--t"></a>pole1: t []

První pole, které má být porovnáno.


### <a name="array2--t"></a>pole2: t []

Druhé pole, které se má porovnat



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

Hodnota, `true` Pokud a `array1` `array2` jsou rovna.
To znamená, že pokud mají obě pole stejnou délku, a všechny prvky jsou stejné jako definované pomocí `equal` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ prvků každého pole.

## <a name="example"></a>Příklad

Následující kód kontroluje, zda jsou různé páry polí stejné:

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a>Poznámky

Tato funkce je definována pro obecné typy. To znamená, že kdykoli máme dvě pole `'T[]` a funkci `equal: ('T, 'T) -> Bool` , tato funkce vrátí `Bool` hodnotu, která označuje, zda jsou pole shodná.
Pro dvě pole, která mají být považována za EQUAL, musí mít stejnou délku a elementy ve stejné pozici v poli musí být stejné.