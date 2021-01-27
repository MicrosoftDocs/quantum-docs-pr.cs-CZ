---
uid: Microsoft.Quantum.Synthesis.FlipMasks
title: FlipMasks – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FlipMasks
qsharp.summary: For every 2-level unitary calculates "flip mask", which denotes qubits which should be inverted before and after applying corresponding 1-qubit gate. For convenience prepends result with 0.
ms.openlocfilehash: ca0ce69b3353379a42cc109cebb32efe4e364825
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859156"
---
# <a name="flipmasks-function"></a>FlipMasks – funkce

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


U každé dvě úrovně 2 se počítá "překlopná maska", která označuje qubits, která se má obrátit před a po použití odpovídající qubit brány.
Pro praktické předřadí výsledek 0.

```qsharp
function FlipMasks (decomposition : (Microsoft.Quantum.Math.Complex[][], Int, Int)[], allQubitsMask : Int) : Int[]
```


## <a name="input"></a>Vstup

### <a name="decomposition--complexintint"></a>dekompozice: ([Complex](xref:Microsoft.Quantum.Math.Complex)[] [],[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []




### <a name="allqubitsmask--int"></a>allQubitsMask: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]

