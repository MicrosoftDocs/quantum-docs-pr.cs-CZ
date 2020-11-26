---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRCA
title: Operace ApplyIfElseRCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRCA
qsharp.summary: ''
ms.openlocfilehash: 6fbf186575775b3ae18a41727c225fb871f8dac0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192617"
---
# <a name="applyifelserca-operation"></a>Operace ApplyIfElseRCA

Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyIfElseRCA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj + Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj + Ctl), oneArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="measurementresult--__invalidresult__"></a>measurementResult: __neplatné <Result>__




### <a name="onresultzeroop--t--unit--is-adj--ctl"></a>onResultZeroOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL




### <a name="zeroarg--t"></a>zeroArg: 'T




### <a name="onresultoneop--u--unit--is-adj--ctl"></a>onResultOneOp: "U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL




### <a name="onearg--u"></a>oneArg: ' U





## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S


### <a name="u"></a>U

