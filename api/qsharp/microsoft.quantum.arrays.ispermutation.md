---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funkce ' permutace '
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705936"
---
# <a name="ispermutation-function"></a>Funkce ' permutace '

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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