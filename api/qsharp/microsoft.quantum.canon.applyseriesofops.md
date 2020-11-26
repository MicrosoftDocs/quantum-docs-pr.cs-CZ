---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Operace ApplySeriesOfOps
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b8810e7d31689046e72905195a3a25ef80fc8d67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217998"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="052d5-102">Operace ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="052d5-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="052d5-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="052d5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="052d5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="052d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="052d5-105">Aplikuje seznam operací OPS a jejich cílů postupně na pole.</span><span class="sxs-lookup"><span data-stu-id="052d5-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="052d5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="052d5-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="052d5-107">listOfOps: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="052d5-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="052d5-108">Seznam operací, přičemž každý z nich vezme pole, které se má použít.</span><span class="sxs-lookup"><span data-stu-id="052d5-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="052d5-109">Jsou aplikované postupně, nejnižšími indexy jako první.</span><span class="sxs-lookup"><span data-stu-id="052d5-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="052d5-110">cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="052d5-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="052d5-111">Vnořená pole popisující cíle pro op.</span><span class="sxs-lookup"><span data-stu-id="052d5-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="052d5-112">Každé pole by mělo obsahovat seznam čísla popisujících indexy, které se mají použít.</span><span class="sxs-lookup"><span data-stu-id="052d5-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="052d5-113">registr: t []</span><span class="sxs-lookup"><span data-stu-id="052d5-113">register : 'T[]</span></span>

<span data-ttu-id="052d5-114">Qubit registrace, na které se má pracovat.</span><span class="sxs-lookup"><span data-stu-id="052d5-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="052d5-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="052d5-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="052d5-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="052d5-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="052d5-117">'S</span><span class="sxs-lookup"><span data-stu-id="052d5-117">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="052d5-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="052d5-118">See Also</span></span>

- [<span data-ttu-id="052d5-119">Microsoft. proApplyOpRepeatedlyOver. Canon.</span><span class="sxs-lookup"><span data-stu-id="052d5-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)