---
uid: Microsoft.Quantum.Canon.RepeatC
title: Operace RepeatC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 8dc178374bdc9f8bf9f8aed57b9ae9a56995dec6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698889"
---
# <a name="repeatc-operation"></a>Operace RepeatC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Opakuje zadaný počet opakování operace.

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--tinput--unit-ctl"></a>op: TInput = seznam CTL>ch [jednotek](xref:microsoft.quantum.lang-ref.unit)

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
- [Microsoft. prodoby. Canon. Repeat](xref:Microsoft.Quantum.Canon.RepeatA)
- [Microsoft. proRepeatCA. Canon.](xref:Microsoft.Quantum.Canon.RepeatCA)