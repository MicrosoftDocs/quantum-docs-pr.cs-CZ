---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: Operace ApplySeriesOfOpsC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: d909aadbfe86f6d1314e9be5434249c40932ae4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705016"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="8a17f-102">Operace ApplySeriesOfOpsC</span><span class="sxs-lookup"><span data-stu-id="8a17f-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="8a17f-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8a17f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8a17f-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8a17f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8a17f-105">Aplikuje seznam operací OPS a jejich cílů postupně na pole.</span><span class="sxs-lookup"><span data-stu-id="8a17f-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="8a17f-106">Kontrol</span><span class="sxs-lookup"><span data-stu-id="8a17f-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8a17f-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="8a17f-107">Input</span></span>

### <a name="listofops--t--unit-ctl"></a><span data-ttu-id="8a17f-108">listOfOps: t [] [=> CTL](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="8a17f-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span></span>

<span data-ttu-id="8a17f-109">Seznam operací, přičemž každý z nich vezme pole, které se má použít.</span><span class="sxs-lookup"><span data-stu-id="8a17f-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="8a17f-110">Jsou aplikované postupně, nejnižšími indexy jako první.</span><span class="sxs-lookup"><span data-stu-id="8a17f-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="8a17f-111">Každý musí mít řízený funktor</span><span class="sxs-lookup"><span data-stu-id="8a17f-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="8a17f-112">cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="8a17f-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="8a17f-113">Vnořená pole popisující cíle pro op.</span><span class="sxs-lookup"><span data-stu-id="8a17f-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="8a17f-114">Každé pole by mělo obsahovat seznam čísla popisujících indexy, které se mají použít.</span><span class="sxs-lookup"><span data-stu-id="8a17f-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="8a17f-115">registr: t []</span><span class="sxs-lookup"><span data-stu-id="8a17f-115">register : 'T[]</span></span>

<span data-ttu-id="8a17f-116">Qubit registrace, na které se má pracovat.</span><span class="sxs-lookup"><span data-stu-id="8a17f-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8a17f-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8a17f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8a17f-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8a17f-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8a17f-119">'S</span><span class="sxs-lookup"><span data-stu-id="8a17f-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="8a17f-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="8a17f-120">See Also</span></span>

- [<span data-ttu-id="8a17f-121">Microsoft. proApplyOpRepeatedlyOver. Canon.</span><span class="sxs-lookup"><span data-stu-id="8a17f-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)