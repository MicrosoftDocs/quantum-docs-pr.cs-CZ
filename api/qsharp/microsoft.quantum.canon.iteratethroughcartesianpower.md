---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Operace IterateThroughCartesianPower
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840301"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="791f5-102">Operace IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="791f5-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="791f5-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="791f5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="791f5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="791f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="791f5-105">Aplikuje operaci pro každý index v kartézském výkonu rozsahu celého čísla.</span><span class="sxs-lookup"><span data-stu-id="791f5-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="791f5-106">Popis</span><span class="sxs-lookup"><span data-stu-id="791f5-106">Description</span></span>

<span data-ttu-id="791f5-107">Iterativní postupně aplikuje operaci pro každý prvek kartézském výkonu rozsahu `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="791f5-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="791f5-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="791f5-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="791f5-109">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="791f5-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="791f5-110">Kartézském napájení, na které `0..(bound - 1)` by měl být rozsah vyvolán.</span><span class="sxs-lookup"><span data-stu-id="791f5-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="791f5-111">Bound: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="791f5-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="791f5-112">Specifikace rozsahu, který se má iterovat, zadaný jako délka rozsahu</span><span class="sxs-lookup"><span data-stu-id="791f5-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="791f5-113">op: [int](xref:microsoft.quantum.lang-ref.int)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="791f5-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="791f5-114">Operace, která má být volána pro každý prvek daného kartézském napájení.</span><span class="sxs-lookup"><span data-stu-id="791f5-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="791f5-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="791f5-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="791f5-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="791f5-116">Example</span></span>

<span data-ttu-id="791f5-117">Vzhledem k operaci `op` jsou tyto dva fragmenty ekvivalentní:</span><span class="sxs-lookup"><span data-stu-id="791f5-117">Given an operation `op`, the following two snippets are equivalent:</span></span>

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a><span data-ttu-id="791f5-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="791f5-118">See Also</span></span>

- [<span data-ttu-id="791f5-119">Microsoft. proIterateThroughCartesianProduct. Canon.</span><span class="sxs-lookup"><span data-stu-id="791f5-119">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)