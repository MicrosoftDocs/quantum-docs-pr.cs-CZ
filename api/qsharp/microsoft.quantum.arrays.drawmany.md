---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Operace DrawMany
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209991"
---
# <a name="drawmany-operation"></a>Operace DrawMany

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Opakuje operaci pro daný počet vzorků a shromažďuje jejich výstupy v poli.

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a>Vstup

### <a name="op--tinput--toutput"></a>op: ' TInput => ' TOutput 

Operace, která se má volat opakovaně


### <a name="nsamples--int"></a>nSamples: [int](xref:microsoft.quantum.lang-ref.int)

Počet vzorků volání `op` ke shromáždění.


### <a name="input--tinput"></a>vstup: ' TInput

Vstup, který má být předán `op` .



## <a name="output--toutput"></a>Výstup: ' TOutput []



## <a name="type-parameters"></a>Parametry typu

### <a name="tinput"></a>'TInput


### <a name="toutput"></a>'TOutput



## <a name="see-also"></a>Viz také

- [Microsoft. v. Canon. Repeat](xref:Microsoft.Quantum.Canon.Repeat)