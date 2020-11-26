---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equals – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 176e15139a27d375fb047c07fa1ee778dc8cc2ce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221364"
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

## <a name="remarks"></a>Poznámky

Tato funkce je definována pro obecné typy. To znamená, že kdykoli máme dvě pole `'T[]` a funkci `equal: ('T, 'T) -> Bool` , tato funkce vrátí `Bool` hodnotu, která označuje, zda jsou pole shodná.
Pro dvě pole, která mají být považována za EQUAL, musí mít stejnou délku a elementy ve stejné pozici v poli musí být stejné.