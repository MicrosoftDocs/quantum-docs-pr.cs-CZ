---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: Operace ApplySeriesOfOpsA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: e5b3527507f79dcc77803ce01472856145df0e9f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217964"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="d104e-102">Operace ApplySeriesOfOpsA</span><span class="sxs-lookup"><span data-stu-id="d104e-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="d104e-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d104e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d104e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d104e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d104e-105">Aplikuje seznam operací OPS a jejich cílů postupně na pole.</span><span class="sxs-lookup"><span data-stu-id="d104e-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="d104e-106">(Sousednít)</span><span class="sxs-lookup"><span data-stu-id="d104e-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="d104e-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="d104e-107">Input</span></span>

### <a name="listofops--t--unit--is-adj"></a><span data-ttu-id="d104e-108">listOfOps: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ []</span><span class="sxs-lookup"><span data-stu-id="d104e-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="d104e-109">Seznam operací, přičemž každý z nich vezme pole, které se má použít.</span><span class="sxs-lookup"><span data-stu-id="d104e-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="d104e-110">Jsou aplikované postupně, nejnižšími indexy jako první.</span><span class="sxs-lookup"><span data-stu-id="d104e-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="d104e-111">Každá z nich musí mít sousední funktor</span><span class="sxs-lookup"><span data-stu-id="d104e-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="d104e-112">cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="d104e-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="d104e-113">Vnořená pole popisující cíle pro op.</span><span class="sxs-lookup"><span data-stu-id="d104e-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="d104e-114">Každé pole by mělo obsahovat seznam čísla popisujících indexy, které se mají použít.</span><span class="sxs-lookup"><span data-stu-id="d104e-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="d104e-115">registr: t []</span><span class="sxs-lookup"><span data-stu-id="d104e-115">register : 'T[]</span></span>

<span data-ttu-id="d104e-116">Qubit registrace, na které se má pracovat.</span><span class="sxs-lookup"><span data-stu-id="d104e-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d104e-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d104e-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d104e-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d104e-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d104e-119">'S</span><span class="sxs-lookup"><span data-stu-id="d104e-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="d104e-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="d104e-120">See Also</span></span>

- [<span data-ttu-id="d104e-121">Microsoft. proApplyOpRepeatedlyOver. Canon.</span><span class="sxs-lookup"><span data-stu-id="d104e-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)