---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: Operace ApplyPermutationUsingDecompositionWithVariableOrder
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: a5ca9b366f7ff477070e21fea047ff04b425439c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203429"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a>Operace ApplyPermutationUsingDecompositionWithVariableOrder

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Permutes amplitudy ve stavu, který má za následek permutaci s využitím syntézy založené na dekompozici.

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Tato operace je obecnější verze, @"microsoft.quantum.synthesis.applypermutationusingdecomposition" ve které lze určit pořadí proměnných. Jiné pořadí proměnných změní pořadí rozkladu a tabulky pravdy používané pro řízené @"microsoft.quantum.intrinsic.x" brány.  Proto změna pořadí proměnných změní počet všech bran používaných k realizaci permutace.

## <a name="input"></a>Vstup

### <a name="perm--int"></a>Perm: [int](xref:microsoft.quantum.lang-ref.int)[]

Permutace prvků $2 ^ n $ počínaje 0.


### <a name="variableorder--int"></a>variableOrder: [int](xref:microsoft.quantum.lang-ref.int)[]

Permutace $n $ prvků od 0.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Seznam $n $ qubits, na který se aplikuje permutace



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. proshrnutí. ApplyPermutationUsingDecomposition](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [Microsoft. proshrnutí. ApplyPermutationUsingTransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)