---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Operace ApplySeriesOfOps
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b086b01b0be86bd25a6d6cdef26bfbb53e484cb2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841498"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="f83fd-102">Operace ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="f83fd-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="f83fd-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f83fd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f83fd-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f83fd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f83fd-105">Aplikuje seznam operací OPS a jejich cílů postupně na pole.</span><span class="sxs-lookup"><span data-stu-id="f83fd-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f83fd-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f83fd-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="f83fd-107">listOfOps: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="f83fd-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="f83fd-108">Seznam operací, přičemž každý z nich vezme pole, které se má použít.</span><span class="sxs-lookup"><span data-stu-id="f83fd-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="f83fd-109">Jsou aplikované postupně, nejnižšími indexy jako první.</span><span class="sxs-lookup"><span data-stu-id="f83fd-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="f83fd-110">cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="f83fd-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="f83fd-111">Vnořená pole popisující cíle pro op.</span><span class="sxs-lookup"><span data-stu-id="f83fd-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="f83fd-112">Každé pole by mělo obsahovat seznam čísla popisujících indexy, které se mají použít.</span><span class="sxs-lookup"><span data-stu-id="f83fd-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="f83fd-113">registr: t []</span><span class="sxs-lookup"><span data-stu-id="f83fd-113">register : 'T[]</span></span>

<span data-ttu-id="f83fd-114">Qubit registrace, na které se má pracovat.</span><span class="sxs-lookup"><span data-stu-id="f83fd-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f83fd-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f83fd-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f83fd-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f83fd-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f83fd-117">'S</span><span class="sxs-lookup"><span data-stu-id="f83fd-117">'T</span></span>



## <a name="example"></a><span data-ttu-id="f83fd-118">Příklad</span><span class="sxs-lookup"><span data-stu-id="f83fd-118">Example</span></span>

<span data-ttu-id="f83fd-119">Následující příkaz použije EXP ([PauliX, PauliY], 0,5) na qubits 0, 1//then X na qubit 2 let OPS = [exp ([PauliX, PauliY], 0,5, _), ApplyToFirstQubit (X, _)]; Povolit indexy = [[0, 1], [2]]; ApplySeriesOfOps (OPS; Indexes; qubitArray);</span><span class="sxs-lookup"><span data-stu-id="f83fd-119">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubit(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOps(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="f83fd-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="f83fd-120">See Also</span></span>

- [<span data-ttu-id="f83fd-121">Microsoft. proApplyOpRepeatedlyOver. Canon.</span><span class="sxs-lookup"><span data-stu-id="f83fd-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)