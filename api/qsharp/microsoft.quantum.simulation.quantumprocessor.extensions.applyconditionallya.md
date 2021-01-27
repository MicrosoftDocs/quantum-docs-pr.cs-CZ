---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: Operace ApplyConditionallyA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: 18ea79e363c28d4fa7aacb69d53a43f6ce39df36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847877"
---
# <a name="applyconditionallya-operation"></a><span data-ttu-id="a13f8-102">Operace ApplyConditionallyA</span><span class="sxs-lookup"><span data-stu-id="a13f8-102">ApplyConditionallyA operation</span></span>

<span data-ttu-id="a13f8-103">Obor názvů: [Microsoft.. simulace. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="a13f8-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="a13f8-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a13f8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="a13f8-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="a13f8-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="a13f8-106">measurementResults: __neplatná <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="a13f8-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="a13f8-107">resultsValues: __neplatná <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="a13f8-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj"></a><span data-ttu-id="a13f8-108">onEqualOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="a13f8-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="a13f8-109">equalArg: 'T</span><span class="sxs-lookup"><span data-stu-id="a13f8-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj"></a><span data-ttu-id="a13f8-110">onNonEqualOp: jednotka U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="a13f8-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="a13f8-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="a13f8-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="a13f8-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a13f8-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a13f8-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a13f8-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a13f8-114">'S</span><span class="sxs-lookup"><span data-stu-id="a13f8-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="a13f8-115">U</span><span class="sxs-lookup"><span data-stu-id="a13f8-115">'U</span></span>

