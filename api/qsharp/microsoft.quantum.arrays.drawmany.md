---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Operace DrawMany
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 601fe603a869dcf977c1ceade5819ee64f634d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706112"
---
# <a name="drawmany-operation"></a>Operace DrawMany

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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