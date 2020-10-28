---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: Operace ApplySeriesOfOpsA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: e2b928fa4c9446e16d2bf5e7b68a32d4bba3a528
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705017"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="74312-102">Operace ApplySeriesOfOpsA</span><span class="sxs-lookup"><span data-stu-id="74312-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="74312-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="74312-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="74312-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="74312-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="74312-105">Aplikuje seznam operací OPS a jejich cílů postupně na pole.</span><span class="sxs-lookup"><span data-stu-id="74312-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="74312-106">(Sousednít)</span><span class="sxs-lookup"><span data-stu-id="74312-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="74312-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="74312-107">Input</span></span>

### <a name="listofops--t--unit-adj"></a><span data-ttu-id="74312-108">listOfOps: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ []</span><span class="sxs-lookup"><span data-stu-id="74312-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="74312-109">Seznam operací, přičemž každý z nich vezme pole, které se má použít.</span><span class="sxs-lookup"><span data-stu-id="74312-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="74312-110">Jsou aplikované postupně, nejnižšími indexy jako první.</span><span class="sxs-lookup"><span data-stu-id="74312-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="74312-111">Každá z nich musí mít sousední funktor</span><span class="sxs-lookup"><span data-stu-id="74312-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="74312-112">cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="74312-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="74312-113">Vnořená pole popisující cíle pro op.</span><span class="sxs-lookup"><span data-stu-id="74312-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="74312-114">Každé pole by mělo obsahovat seznam čísla popisujících indexy, které se mají použít.</span><span class="sxs-lookup"><span data-stu-id="74312-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="74312-115">registr: t []</span><span class="sxs-lookup"><span data-stu-id="74312-115">register : 'T[]</span></span>

<span data-ttu-id="74312-116">Qubit registrace, na které se má pracovat.</span><span class="sxs-lookup"><span data-stu-id="74312-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="74312-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="74312-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="74312-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="74312-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="74312-119">'S</span><span class="sxs-lookup"><span data-stu-id="74312-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="74312-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="74312-120">See Also</span></span>

- [<span data-ttu-id="74312-121">Microsoft. proApplyOpRepeatedlyOver. Canon.</span><span class="sxs-lookup"><span data-stu-id="74312-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)