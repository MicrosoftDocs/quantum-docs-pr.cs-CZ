---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: Operace ApplySeriesOfOpsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 2327a693e528cf46f95eae5ee052e9dd9b6ee187
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705008"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="0a642-102">Operace ApplySeriesOfOpsCA</span><span class="sxs-lookup"><span data-stu-id="0a642-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="0a642-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0a642-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0a642-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0a642-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0a642-105">Aplikuje seznam operací OPS a jejich cílů postupně na pole.</span><span class="sxs-lookup"><span data-stu-id="0a642-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="0a642-106">(Sousední a řízený)</span><span class="sxs-lookup"><span data-stu-id="0a642-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0a642-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="0a642-107">Input</span></span>

### <a name="listofops--t--unit-adj--ctl"></a><span data-ttu-id="0a642-108">listOfOps: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="0a642-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="0a642-109">Seznam operací, přičemž každý z nich vezme pole, které se má použít.</span><span class="sxs-lookup"><span data-stu-id="0a642-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="0a642-110">Jsou aplikované postupně, nejnižšími indexy jako první.</span><span class="sxs-lookup"><span data-stu-id="0a642-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="0a642-111">Každá z nich musí mít sousední i řízený funktor.</span><span class="sxs-lookup"><span data-stu-id="0a642-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="0a642-112">cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="0a642-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="0a642-113">Vnořená pole popisující cíle pro op.</span><span class="sxs-lookup"><span data-stu-id="0a642-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="0a642-114">Každé pole by mělo obsahovat seznam čísla popisujících indexy, které se mají použít.</span><span class="sxs-lookup"><span data-stu-id="0a642-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="0a642-115">registr: t []</span><span class="sxs-lookup"><span data-stu-id="0a642-115">register : 'T[]</span></span>

<span data-ttu-id="0a642-116">Qubit registrace, na které se má pracovat.</span><span class="sxs-lookup"><span data-stu-id="0a642-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0a642-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0a642-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0a642-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="0a642-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0a642-119">'S</span><span class="sxs-lookup"><span data-stu-id="0a642-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="0a642-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="0a642-120">See Also</span></span>

- [<span data-ttu-id="0a642-121">Microsoft. proApplyOpRepeatedlyOver. Canon.</span><span class="sxs-lookup"><span data-stu-id="0a642-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)