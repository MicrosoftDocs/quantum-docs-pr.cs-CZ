---
uid: Microsoft.Quantum.Canon.Repeat
title: Opakovat operaci
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5aedd056b851b8d8d7c25a32eb22587292e132a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698901"
---
# <a name="repeat-operation"></a>Opakovat operaci

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


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