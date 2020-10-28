---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: Operace ApplyConditionallyA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: b6f7e7d6d51e531b0ec9e7e4f2f5772038421933
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697453"
---
# <a name="applyconditionallya-operation"></a><span data-ttu-id="79d98-102">Operace ApplyConditionallyA</span><span class="sxs-lookup"><span data-stu-id="79d98-102">ApplyConditionallyA operation</span></span>

<span data-ttu-id="79d98-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="79d98-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="79d98-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="79d98-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="79d98-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="79d98-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="79d98-106">measurementResults: __neplatná <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="79d98-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="79d98-107">resultsValues: __neplatná <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="79d98-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--t--unit-adj"></a><span data-ttu-id="79d98-108">onEqualOp: t [=> ADJ](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="79d98-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="79d98-109">equalArg: 'T</span><span class="sxs-lookup"><span data-stu-id="79d98-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit-adj"></a><span data-ttu-id="79d98-110">onNonEqualOp: ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="79d98-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="79d98-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="79d98-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="79d98-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="79d98-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="79d98-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="79d98-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="79d98-114">'S</span><span class="sxs-lookup"><span data-stu-id="79d98-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="79d98-115">U</span><span class="sxs-lookup"><span data-stu-id="79d98-115">'U</span></span>

