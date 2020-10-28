---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicC
title: Operace ApplyConditionallyIntrinsicC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicC
qsharp.summary: ''
ms.openlocfilehash: 54367d89636eb69462040e83cc3c4b6a9f734c0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706624"
---
# <a name="applyconditionallyintrinsicc-operation"></a><span data-ttu-id="fc178-102">Operace ApplyConditionallyIntrinsicC</span><span class="sxs-lookup"><span data-stu-id="fc178-102">ApplyConditionallyIntrinsicC operation</span></span>

<span data-ttu-id="fc178-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="fc178-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="fc178-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fc178-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicC (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl), onNonEqualOp : (Unit => Unit is Ctl)) : Unit
```


## <a name="input"></a><span data-ttu-id="fc178-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="fc178-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="fc178-106">measurementResults: __neplatná <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="fc178-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="fc178-107">resultsValues: __neplatná <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="fc178-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--unit--unit-ctl"></a><span data-ttu-id="fc178-108">onEqualOp: [Unit](xref:microsoft.quantum.lang-ref.unit) => seznam CTL [pro jednotky](xref:microsoft.quantum.lang-ref.unit) jednotek</span><span class="sxs-lookup"><span data-stu-id="fc178-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="onnonequalop--unit--unit-ctl"></a><span data-ttu-id="fc178-109">onNonEqualOp: [Unit](xref:microsoft.quantum.lang-ref.unit) => seznam CTL [pro jednotky](xref:microsoft.quantum.lang-ref.unit) jednotek</span><span class="sxs-lookup"><span data-stu-id="fc178-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="fc178-110">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc178-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

