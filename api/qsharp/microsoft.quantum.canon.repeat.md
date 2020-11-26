---
uid: Microsoft.Quantum.Canon.Repeat
title: Opakovat operaci
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: cd572e5e082df94d762a0869ad2c1923fb71fd3d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205588"
---
# <a name="repeat-operation"></a>Opakovat operaci

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Opakuje zadaný počet opakování operace.

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--tinput--unit"></a>op: TInput => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

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
- [Microsoft. prodoby. Canon. Repeat](xref:Microsoft.Quantum.Canon.RepeatA)
- [Microsoft. proRepeatC. Canon.](xref:Microsoft.Quantum.Canon.RepeatC)
- [Microsoft. proRepeatCA. Canon.](xref:Microsoft.Quantum.Canon.RepeatCA)