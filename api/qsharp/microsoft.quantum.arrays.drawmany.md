---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Operace DrawMany
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846208"
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



## <a name="example"></a>Příklad

Následující ukázky celé číslo, s ohledem na operaci, která v jednom okamžiku vyčísluje jeden bit.

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a>Viz také

- [Microsoft. v. Canon. Repeat](xref:Microsoft.Quantum.Canon.Repeat)