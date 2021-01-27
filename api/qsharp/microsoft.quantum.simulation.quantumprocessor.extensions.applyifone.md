---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOne
title: Operace ApplyIfOne
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOne
qsharp.summary: ''
ms.openlocfilehash: fd5ee65615e4910d60db83cb8ec4201cfff9035d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855590"
---
# <a name="applyifone-operation"></a><span data-ttu-id="96073-102">Operace ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="96073-102">ApplyIfOne operation</span></span>

<span data-ttu-id="96073-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="96073-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="96073-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="96073-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOne<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="96073-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="96073-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="96073-106">measurementResult: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="96073-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit"></a><span data-ttu-id="96073-107">onResultOneOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="96073-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--t"></a><span data-ttu-id="96073-108">oneArg: 'T</span><span class="sxs-lookup"><span data-stu-id="96073-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="96073-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="96073-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="96073-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="96073-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="96073-111">'S</span><span class="sxs-lookup"><span data-stu-id="96073-111">'T</span></span>

