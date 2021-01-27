---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneA
title: Operace ApplyIfOneA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneA
qsharp.summary: ''
ms.openlocfilehash: 63ce44300f6e50cb91294b62611275e3e8942655
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855617"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="bcde2-102">Operace ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="bcde2-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="bcde2-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="bcde2-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="bcde2-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bcde2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Adj), oneArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="bcde2-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="bcde2-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="bcde2-106">measurementResult: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="bcde2-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-adj"></a><span data-ttu-id="bcde2-107">onResultOneOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="bcde2-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="bcde2-108">oneArg: 'T</span><span class="sxs-lookup"><span data-stu-id="bcde2-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="bcde2-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bcde2-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bcde2-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="bcde2-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bcde2-111">'S</span><span class="sxs-lookup"><span data-stu-id="bcde2-111">'T</span></span>

