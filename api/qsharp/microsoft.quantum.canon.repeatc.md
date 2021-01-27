---
uid: Microsoft.Quantum.Canon.RepeatC
title: Operace RepeatC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: efb820411be63352fc09ada2441a9140dd5575f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840235"
---
# <a name="repeatc-operation"></a>Operace RepeatC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Opakuje zadaný počet opakování operace.

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit is Ctl
```


## <a name="input"></a>Vstup

### <a name="op--tinput--unit--is-ctl"></a>op: TInput => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL

Operace, která se má volat opakovaně


### <a name="ntimes--int"></a>nTimes: [int](xref:microsoft.quantum.lang-ref.int)

Počet pokusů o volání `op` .


### <a name="input--tinput"></a>vstup: ' TInput

Vstup, který má být předán `op` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="tinput"></a>'TInput



## <a name="example"></a>Příklad

Následují ekvivalenty:

```qsharp
RepeatC(U, 17, target);
(BoundC(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a>Viz také

- [Microsoft. Forms. Arrays. DrawMany](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Microsoft. v. Canon. Repeat](xref:Microsoft.Quantum.Canon.Repeat)
- [Microsoft. prodoby. Canon. Repeat](xref:Microsoft.Quantum.Canon.RepeatA)
- [Microsoft. proRepeatCA. Canon.](xref:Microsoft.Quantum.Canon.RepeatCA)