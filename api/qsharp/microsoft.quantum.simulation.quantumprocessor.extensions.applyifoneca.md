---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneCA
title: Operace ApplyIfOneCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneCA
qsharp.summary: ''
ms.openlocfilehash: e997cf4b20fdd2c52285191b732297ca99886c22
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230935"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="0965e-102">Operace ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="0965e-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="0965e-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="0965e-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="0965e-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0965e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneCA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl + Adj), oneArg : 'T)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0965e-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="0965e-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="0965e-106">measurementResult: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="0965e-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-adj--ctl"></a><span data-ttu-id="0965e-107">onResultOneOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="0965e-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="onearg--t"></a><span data-ttu-id="0965e-108">oneArg: 'T</span><span class="sxs-lookup"><span data-stu-id="0965e-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="0965e-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0965e-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0965e-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="0965e-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0965e-111">'S</span><span class="sxs-lookup"><span data-stu-id="0965e-111">'T</span></span>

