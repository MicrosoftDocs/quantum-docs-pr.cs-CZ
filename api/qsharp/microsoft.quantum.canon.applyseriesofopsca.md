---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: Operace ApplySeriesOfOpsCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 9a1f6189428b086c38b1d0f289afb18c2cf1be40
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850865"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="94a77-102">Operace ApplySeriesOfOpsCA</span><span class="sxs-lookup"><span data-stu-id="94a77-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="94a77-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="94a77-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="94a77-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94a77-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94a77-105">Aplikuje seznam operací OPS a jejich cílů postupně na pole.</span><span class="sxs-lookup"><span data-stu-id="94a77-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="94a77-106">(Sousední a řízený)</span><span class="sxs-lookup"><span data-stu-id="94a77-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="94a77-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="94a77-107">Input</span></span>

### <a name="listofops--t--unit--is-adj--ctl"></a><span data-ttu-id="94a77-108">listOfOps: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="94a77-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="94a77-109">Seznam operací, přičemž každý z nich vezme pole, které se má použít.</span><span class="sxs-lookup"><span data-stu-id="94a77-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="94a77-110">Jsou aplikované postupně, nejnižšími indexy jako první.</span><span class="sxs-lookup"><span data-stu-id="94a77-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="94a77-111">Každá z nich musí mít sousední i řízený funktor.</span><span class="sxs-lookup"><span data-stu-id="94a77-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="94a77-112">cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="94a77-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="94a77-113">Vnořená pole popisující cíle pro op.</span><span class="sxs-lookup"><span data-stu-id="94a77-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="94a77-114">Každé pole by mělo obsahovat seznam čísla popisujících indexy, které se mají použít.</span><span class="sxs-lookup"><span data-stu-id="94a77-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="94a77-115">registr: t []</span><span class="sxs-lookup"><span data-stu-id="94a77-115">register : 'T[]</span></span>

<span data-ttu-id="94a77-116">Qubit registrace, na které se má pracovat.</span><span class="sxs-lookup"><span data-stu-id="94a77-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="94a77-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94a77-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="94a77-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="94a77-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="94a77-119">'S</span><span class="sxs-lookup"><span data-stu-id="94a77-119">'T</span></span>



## <a name="example"></a><span data-ttu-id="94a77-120">Příklad</span><span class="sxs-lookup"><span data-stu-id="94a77-120">Example</span></span>

<span data-ttu-id="94a77-121">Následující příkaz použije EXP ([PauliX, PauliY], 0,5) na qubits 0, 1//then X na qubit 2 let OPS = [exp ([PauliX, PauliY], 0,5, _), ApplyToFirstQubitCA (X, _)]; Povolit indexy = [[0, 1], [2]]; ApplySeriesOfOpsCA (OPS; Indexes; qubitArray);</span><span class="sxs-lookup"><span data-stu-id="94a77-121">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubitCA(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOpsCA(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="94a77-122">Viz také</span><span class="sxs-lookup"><span data-stu-id="94a77-122">See Also</span></span>

- [<span data-ttu-id="94a77-123">Microsoft. proApplyOpRepeatedlyOver. Canon.</span><span class="sxs-lookup"><span data-stu-id="94a77-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)