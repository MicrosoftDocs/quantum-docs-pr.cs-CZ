---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: Operace ApplyConditionally
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: 24d52576d2fb3e83f294874be4b0d1cd6a80f188
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229065"
---
# <a name="applyconditionally-operation"></a><span data-ttu-id="5ac42-102">Operace ApplyConditionally</span><span class="sxs-lookup"><span data-stu-id="5ac42-102">ApplyConditionally operation</span></span>

<span data-ttu-id="5ac42-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="5ac42-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="5ac42-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5ac42-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="5ac42-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="5ac42-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="5ac42-106">measurementResults: __neplatná <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="5ac42-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="5ac42-107">resultsValues: __neplatná <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="5ac42-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit"></a><span data-ttu-id="5ac42-108">onEqualOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5ac42-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="equalarg--t"></a><span data-ttu-id="5ac42-109">equalArg: 'T</span><span class="sxs-lookup"><span data-stu-id="5ac42-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit"></a><span data-ttu-id="5ac42-110">onNonEqualOp: [jednotka](xref:microsoft.quantum.lang-ref.unit) U =></span><span class="sxs-lookup"><span data-stu-id="5ac42-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="nonequalarg--u"></a><span data-ttu-id="5ac42-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="5ac42-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="5ac42-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5ac42-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5ac42-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5ac42-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5ac42-114">'S</span><span class="sxs-lookup"><span data-stu-id="5ac42-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="5ac42-115">U</span><span class="sxs-lookup"><span data-stu-id="5ac42-115">'U</span></span>

