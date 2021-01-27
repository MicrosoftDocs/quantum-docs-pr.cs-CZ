---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: Operace ApplyConditionallyC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: 09496d384a70fa9fb6826304ce9909034297a118
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847857"
---
# <a name="applyconditionallyc-operation"></a>Operace ApplyConditionallyC

Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionallyC<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl), nonEqualArg : 'U)) : Unit is Ctl
```


## <a name="input"></a>Vstup

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __neplatná <Result>__[]




### <a name="resultsvalues--__invalidresult__"></a>resultsValues: __neplatná <Result>__[]




### <a name="onequalop--t--unit--is-ctl"></a>onEqualOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL




### <a name="equalarg--t"></a>equalArg: 'T




### <a name="onnonequalop--u--unit--is-ctl"></a>onNonEqualOp: U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL.




### <a name="nonequalarg--u"></a>nonEqualArg: ' U





## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S


### <a name="u"></a>U

