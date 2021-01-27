---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funkce ' permutace '
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848095"
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



## <a name="example"></a>Příklad

Následující kód Q # vytiskne zprávu "všechna Diagnostika byla úspěšně dokončena":

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a>Poznámky

Pole s nulovou délkou je triviální permutace.