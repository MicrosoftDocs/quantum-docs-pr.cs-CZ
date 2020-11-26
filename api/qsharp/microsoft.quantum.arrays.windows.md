---
uid: Microsoft.Quantum.Arrays.Windows
title: Funkce Windows
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 8f32a23aa4379744b84c3b8d9c8f565e61c3c64e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219885"
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