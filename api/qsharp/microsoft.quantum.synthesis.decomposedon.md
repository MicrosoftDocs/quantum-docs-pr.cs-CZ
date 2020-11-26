---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: 79f952e7bc7ba9f5337cf5e7a625e0d270a2e17a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203225"
---
# <a name="decomposedon-function"></a>DecomposedOn – funkce

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vytvoří permutaci pro proměnnou.

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>Popis

Pokud je zadána permutace $ \pi $ ( `perm` ) a index $i $ ( `index` ), tato metoda vrátí tři permutace $ ((\ pi_l, \ pi_r), \pi ') $ tak, že obrázky $ \ pi_l $ a $ \ pi_r $ nemění bity v jejich prvcích v jiných rejstřících než $i $ a image $ \pi $ nemění bitovou $i $ ve svých prvcích.

## <a name="input"></a>Vstup

### <a name="perm--int"></a>Perm: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Výstup: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])

