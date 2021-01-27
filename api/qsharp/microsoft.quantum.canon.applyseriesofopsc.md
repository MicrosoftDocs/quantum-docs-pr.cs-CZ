---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: Operace ApplySeriesOfOpsC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: 308256833dc607f685e3a5f2278e374cf3b6ce22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844647"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="fecb0-102">Operace ApplySeriesOfOpsC</span><span class="sxs-lookup"><span data-stu-id="fecb0-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="fecb0-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fecb0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fecb0-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fecb0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fecb0-105">Aplikuje seznam operací OPS a jejich cílů postupně na pole.</span><span class="sxs-lookup"><span data-stu-id="fecb0-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="fecb0-106">Kontrol</span><span class="sxs-lookup"><span data-stu-id="fecb0-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="fecb0-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="fecb0-107">Input</span></span>

### <a name="listofops--t--unit--is-ctl"></a><span data-ttu-id="fecb0-108">listOfOps: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je CTL []</span><span class="sxs-lookup"><span data-stu-id="fecb0-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="fecb0-109">Seznam operací, přičemž každý z nich vezme pole, které se má použít.</span><span class="sxs-lookup"><span data-stu-id="fecb0-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="fecb0-110">Jsou aplikované postupně, nejnižšími indexy jako první.</span><span class="sxs-lookup"><span data-stu-id="fecb0-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="fecb0-111">Každý musí mít řízený funktor</span><span class="sxs-lookup"><span data-stu-id="fecb0-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="fecb0-112">cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="fecb0-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="fecb0-113">Vnořená pole popisující cíle pro op.</span><span class="sxs-lookup"><span data-stu-id="fecb0-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="fecb0-114">Každé pole by mělo obsahovat seznam čísla popisujících indexy, které se mají použít.</span><span class="sxs-lookup"><span data-stu-id="fecb0-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="fecb0-115">registr: t []</span><span class="sxs-lookup"><span data-stu-id="fecb0-115">register : 'T[]</span></span>

<span data-ttu-id="fecb0-116">Qubit registrace, na které se má pracovat.</span><span class="sxs-lookup"><span data-stu-id="fecb0-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fecb0-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fecb0-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fecb0-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="fecb0-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fecb0-119">'S</span><span class="sxs-lookup"><span data-stu-id="fecb0-119">'T</span></span>



## <a name="example"></a><span data-ttu-id="fecb0-120">Příklad</span><span class="sxs-lookup"><span data-stu-id="fecb0-120">Example</span></span>

<span data-ttu-id="fecb0-121">Následující příkaz použije EXP ([PauliX, PauliY], 0,5) na qubits 0, 1//then X na qubit 2 let OPS = [exp ([PauliX, PauliY], 0,5, _), ApplyToFirstQubitC (X, _)]; Povolit indexy = [[0, 1], [2]]; ApplySeriesOfOpsC (OPS; Indexes; qubitArray);</span><span class="sxs-lookup"><span data-stu-id="fecb0-121">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubitC(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOpsC(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="fecb0-122">Viz také</span><span class="sxs-lookup"><span data-stu-id="fecb0-122">See Also</span></span>

- [<span data-ttu-id="fecb0-123">Microsoft. proApplyOpRepeatedlyOver. Canon.</span><span class="sxs-lookup"><span data-stu-id="fecb0-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)