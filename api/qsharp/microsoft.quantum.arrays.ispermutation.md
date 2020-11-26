---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funkce ' permutace '
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 144f683818b5d75de5b075328365d3e994de29d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220922"
---
# <a name="ispermutation-function"></a>Funkce ' permutace '

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí výstupy true, pokud dané pole představuje permutaci.

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a>Popis

Vzhledem k poli `array` délky `n` vrátí hodnotu true pouze v případě, že se každé celé číslo od `0` do `n - 1` stejného zobrazení nachází v `array` , což `array` může být interpretováno jako permutace u `n` elementů.

## <a name="input"></a>Vstup

### <a name="permuation--int"></a>permuation: [int](xref:microsoft.quantum.lang-ref.int)[]

Pole, které může nebo nemusí představovat permutaci.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)



## <a name="remarks"></a>Poznámky

Pole s nulovou délkou je triviální permutace.