---
uid: Microsoft.Quantum.Arrays.Windows
title: Funkce Windows
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: adfea2b9a2f6c22446817538d29586284dba723e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842195"
---
# <a name="windows-function"></a>Funkce Windows

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí všechna po sobě následující podpole délky `size` .

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a>Popis

Tato funkce vrací všechna `n - size + 1` podpole délky `size` v pořadí, kde `n` je délka `arr` .
První podpole jsou až do `arr[0..size - 1], arr[1..size], arr[2..size + 1]` posledního podpole `arr[n - size..n - 1]` .

Pokud `size <= 0` `size > n` je nebo, vrátí se prázdné pole.

## <a name="input"></a>Vstup

### <a name="size--int"></a>Velikost: [int](xref:microsoft.quantum.lang-ref.int)

Délka podpole.


### <a name="array--t"></a>Array: t []

Pole prvků.



## <a name="output--t"></a>Výstup: t [] []



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ `array` prvků.

## <a name="example"></a>Příklad

```qsharp
// same as [[1, 2, 3], [2, 3, 4], [3, 4, 5]]
let windows = Windows(3, [1, 2, 3, 4, 5]);
```