---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: Operace ApplyConditionallyA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: 8117fd632b78c24c9ecb8545274eaf296645b645
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230408"
---
# <a name="applyconditionallya-operation"></a><span data-ttu-id="d7874-102">Operace ApplyConditionallyA</span><span class="sxs-lookup"><span data-stu-id="d7874-102">ApplyConditionallyA operation</span></span>

<span data-ttu-id="d7874-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="d7874-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="d7874-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d7874-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="d7874-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="d7874-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="d7874-106">measurementResults: __neplatná <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="d7874-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="d7874-107">resultsValues: __neplatná <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="d7874-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj"></a><span data-ttu-id="d7874-108">onEqualOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="d7874-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="d7874-109">equalArg: 'T</span><span class="sxs-lookup"><span data-stu-id="d7874-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj"></a><span data-ttu-id="d7874-110">onNonEqualOp: jednotka U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="d7874-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="d7874-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="d7874-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="d7874-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7874-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d7874-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d7874-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d7874-114">'S</span><span class="sxs-lookup"><span data-stu-id="d7874-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="d7874-115">U</span><span class="sxs-lookup"><span data-stu-id="d7874-115">'U</span></span>

