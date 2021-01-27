---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicA
title: Operace ApplyConditionallyIntrinsicA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicA
qsharp.summary: ''
ms.openlocfilehash: b22cb94a835f0504116e7152a4a1bfe66c483c10
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858523"
---
# <a name="applyconditionallyintrinsica-operation"></a><span data-ttu-id="90d0a-102">Operace ApplyConditionallyIntrinsicA</span><span class="sxs-lookup"><span data-stu-id="90d0a-102">ApplyConditionallyIntrinsicA operation</span></span>

<span data-ttu-id="90d0a-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="90d0a-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="90d0a-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="90d0a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Adj), onNonEqualOp : (Unit => Unit is Adj)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="90d0a-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="90d0a-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="90d0a-106">measurementResults: __neplatná <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="90d0a-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="90d0a-107">resultsValues: __neplatná <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="90d0a-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--unit--unit--is-adj"></a><span data-ttu-id="90d0a-108">onEqualOp: jednotka [jednotky](xref:microsoft.quantum.lang-ref.unit) => [](xref:microsoft.quantum.lang-ref.unit) je ADJ.</span><span class="sxs-lookup"><span data-stu-id="90d0a-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onnonequalop--unit--unit--is-adj"></a><span data-ttu-id="90d0a-109">onNonEqualOp: jednotka [jednotky](xref:microsoft.quantum.lang-ref.unit) => [](xref:microsoft.quantum.lang-ref.unit) je ADJ.</span><span class="sxs-lookup"><span data-stu-id="90d0a-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>





## <a name="output--unit"></a><span data-ttu-id="90d0a-110">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="90d0a-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

