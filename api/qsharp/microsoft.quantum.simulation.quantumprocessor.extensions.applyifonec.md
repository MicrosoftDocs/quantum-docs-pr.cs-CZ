---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneC
title: Operace ApplyIfOneC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneC
qsharp.summary: ''
ms.openlocfilehash: ae6e0d16424e745303b377e70927cda847d2f1e8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858743"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="3694b-102">Operace ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="3694b-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="3694b-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="3694b-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="3694b-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3694b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneC<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl), oneArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="3694b-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="3694b-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="3694b-106">measurementResult: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="3694b-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-ctl"></a><span data-ttu-id="3694b-107">onResultOneOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="3694b-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onearg--t"></a><span data-ttu-id="3694b-108">oneArg: 'T</span><span class="sxs-lookup"><span data-stu-id="3694b-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="3694b-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3694b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3694b-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="3694b-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3694b-111">'S</span><span class="sxs-lookup"><span data-stu-id="3694b-111">'T</span></span>

