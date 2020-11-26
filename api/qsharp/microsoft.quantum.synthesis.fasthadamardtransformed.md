---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203089"
---
# <a name="fasthadamardtransformed-function"></a>FastHadamardTransformed – funkce

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vypočítá Hadamard transformaci logické funkce v {-1,1} kódování pomocí metody Yates.

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a>Vstup

### <a name="func--int"></a>Func: [int](xref:microsoft.quantum.lang-ref.int)[]

Tabulka pravdy v {-1,1} kódování



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]

Spektrální koeficienty funkce