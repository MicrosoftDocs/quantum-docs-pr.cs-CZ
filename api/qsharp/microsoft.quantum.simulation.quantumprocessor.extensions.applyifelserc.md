---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRC
title: Operace ApplyIfElseRC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRC
qsharp.summary: ''
ms.openlocfilehash: 21069c43c16bc9712973ac4e0afea8320c0d83a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697149"
---
# <a name="applyifelserc-operation"></a>Operace ApplyIfElseRC

Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Balíček [](https://nuget.org/packages/)




```qsharp
operation ApplyIfElseRC<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Ctl), oneArg : 'U)) : Unit
```


## <a name="input"></a>Vstup

### <a name="measurementresult--__invalidresult__"></a>measurementResult: __neplatné <Result>__




### <a name="onresultzeroop--t--unit-ctl"></a>onResultZeroOp: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL




### <a name="zeroarg--t"></a>zeroArg: 'T




### <a name="onresultoneop--u--unit-ctl"></a>onResultOneOp: U [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL




### <a name="onearg--u"></a>oneArg: ' U





## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S


### <a name="u"></a>U

