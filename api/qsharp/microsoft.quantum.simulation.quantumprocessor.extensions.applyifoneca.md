---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneCA
title: Operace ApplyIfOneCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneCA
qsharp.summary: ''
ms.openlocfilehash: d8f388698c0c6d1557c7903ec68b317728986031
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709376"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="7615d-102">Operace ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="7615d-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="7615d-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="7615d-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="7615d-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7615d-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfOneCA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl + Adj), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="7615d-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="7615d-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="7615d-106">measurementResult: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="7615d-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit-ctl--adj"></a><span data-ttu-id="7615d-107">onResultOneOp: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL a ADJ</span><span class="sxs-lookup"><span data-stu-id="7615d-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="7615d-108">oneArg: 'T</span><span class="sxs-lookup"><span data-stu-id="7615d-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="7615d-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7615d-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7615d-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7615d-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7615d-111">'S</span><span class="sxs-lookup"><span data-stu-id="7615d-111">'T</span></span>

