---
uid: Microsoft.Quantum.Arrays.Windows
title: Funkce Windows
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705696"
---
# <a name="windows-function"></a>Funkce Windows

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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