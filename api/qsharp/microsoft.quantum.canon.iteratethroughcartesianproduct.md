---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Operace IterateThroughCartesianProduct
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: a0aaa8ef6aa6798d31c810254c92820f8136800c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840280"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="206bd-102">Operace IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="206bd-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="206bd-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="206bd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="206bd-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="206bd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="206bd-105">Aplikuje operaci pro každý index v kartézském produktu v několika oblastech.</span><span class="sxs-lookup"><span data-stu-id="206bd-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="206bd-106">Popis</span><span class="sxs-lookup"><span data-stu-id="206bd-106">Description</span></span>

<span data-ttu-id="206bd-107">Iterativní postupně aplikuje operaci pro každý prvek kartézském produktu `0..(bounds[0] - 1)` , `0..(bounds[1] - 1)` ,..., `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="206bd-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="206bd-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="206bd-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="206bd-109">meze: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="206bd-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="206bd-110">Pole určující rozsahy, které se mají iterovat, přičemž každý rozsah je zadaný jako celočíselná délka.</span><span class="sxs-lookup"><span data-stu-id="206bd-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="206bd-111">op: [int](xref:microsoft.quantum.lang-ref.int)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="206bd-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="206bd-112">Operace, která má být volána pro každý prvek daného kartézském produktu.</span><span class="sxs-lookup"><span data-stu-id="206bd-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="206bd-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="206bd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="206bd-114">Příklad</span><span class="sxs-lookup"><span data-stu-id="206bd-114">Example</span></span>

<span data-ttu-id="206bd-115">Vzhledem k operaci `op` jsou tyto dva fragmenty ekvivalentní:</span><span class="sxs-lookup"><span data-stu-id="206bd-115">Given an operation `op`, the following two snippets are equivalent:</span></span>

```qsharp
IterateThroughCartesianProduct([3, 4, 5], op);
```

```qsharp
op([0, 0, 0]);
op([1, 0, 0]);
op([2, 0, 0]);
op([0, 1, 0]);
// ...
op([0, 3, 0]);
op([0, 0, 1]);
//
op([2, 3, 4]);
```

## <a name="see-also"></a><span data-ttu-id="206bd-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="206bd-116">See Also</span></span>

- [<span data-ttu-id="206bd-117">Microsoft. proIterateThroughCartesianPower. Canon.</span><span class="sxs-lookup"><span data-stu-id="206bd-117">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)