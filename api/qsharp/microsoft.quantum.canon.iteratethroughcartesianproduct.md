---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Operace IterateThroughCartesianProduct
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: 6340c7a972253e6f583a3856df93a7066ced3139
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206438"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="f27ed-102">Operace IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="f27ed-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="f27ed-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f27ed-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f27ed-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f27ed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f27ed-105">Aplikuje operaci pro každý index v kartézském produktu v několika oblastech.</span><span class="sxs-lookup"><span data-stu-id="f27ed-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="f27ed-106">Popis</span><span class="sxs-lookup"><span data-stu-id="f27ed-106">Description</span></span>

<span data-ttu-id="f27ed-107">Iterativní postupně aplikuje operaci pro každý prvek kartézském produktu `0..(bounds[0] - 1)` , `0..(bounds[1] - 1)` ,..., `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="f27ed-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="f27ed-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="f27ed-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="f27ed-109">meze: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f27ed-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f27ed-110">Pole určující rozsahy, které se mají iterovat, přičemž každý rozsah je zadaný jako celočíselná délka.</span><span class="sxs-lookup"><span data-stu-id="f27ed-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="f27ed-111">op: [int](xref:microsoft.quantum.lang-ref.int)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f27ed-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f27ed-112">Operace, která má být volána pro každý prvek daného kartézském produktu.</span><span class="sxs-lookup"><span data-stu-id="f27ed-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f27ed-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f27ed-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="f27ed-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="f27ed-114">See Also</span></span>

- [<span data-ttu-id="f27ed-115">Microsoft. proIterateThroughCartesianPower. Canon.</span><span class="sxs-lookup"><span data-stu-id="f27ed-115">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)