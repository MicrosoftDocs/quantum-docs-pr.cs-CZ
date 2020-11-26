---
uid: Microsoft.Quantum.Canon.RepeatA
title: Operace opakování
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5f418f67d7265d4cb39b3636906c74d33d80f472
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205553"
---
# <a name="repeata-operation"></a>Operace opakování

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Opakuje zadaný počet opakování operace.

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a>Vstup

### <a name="op--tinput--unit--is-adj"></a>op: TInput => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace, která se má volat opakovaně


### <a name="ntimes--int"></a>nTimes: [int](xref:microsoft.quantum.lang-ref.int)

Počet pokusů o volání `op` .


### <a name="input--tinput"></a>vstup: ' TInput

Vstup, který má být předán `op` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="tinput"></a>'TInput



## <a name="see-also"></a>Viz také

- [Microsoft. Forms. Arrays. DrawMany](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Microsoft. v. Canon. Repeat](xref:Microsoft.Quantum.Canon.Repeat)
- [Microsoft. proRepeatC. Canon.](xref:Microsoft.Quantum.Canon.RepeatC)
- [Microsoft. proRepeatCA. Canon.](xref:Microsoft.Quantum.Canon.RepeatCA)