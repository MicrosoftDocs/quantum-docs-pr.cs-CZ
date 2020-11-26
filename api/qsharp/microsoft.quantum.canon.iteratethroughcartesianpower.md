---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Operace IterateThroughCartesianPower
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 2883e7cb30633afe51d380befe806665207c5abd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206472"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="9156f-102">Operace IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="9156f-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="9156f-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9156f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9156f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9156f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9156f-105">Aplikuje operaci pro každý index v kartézském výkonu rozsahu celého čísla.</span><span class="sxs-lookup"><span data-stu-id="9156f-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="9156f-106">Popis</span><span class="sxs-lookup"><span data-stu-id="9156f-106">Description</span></span>

<span data-ttu-id="9156f-107">Iterativní postupně aplikuje operaci pro každý prvek kartézském výkonu rozsahu `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="9156f-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="9156f-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="9156f-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="9156f-109">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9156f-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9156f-110">Kartézském napájení, na které `0..(bound - 1)` by měl být rozsah vyvolán.</span><span class="sxs-lookup"><span data-stu-id="9156f-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="9156f-111">Bound: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9156f-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9156f-112">Specifikace rozsahu, který se má iterovat, zadaný jako délka rozsahu</span><span class="sxs-lookup"><span data-stu-id="9156f-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="9156f-113">op: [int](xref:microsoft.quantum.lang-ref.int)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9156f-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9156f-114">Operace, která má být volána pro každý prvek daného kartézském napájení.</span><span class="sxs-lookup"><span data-stu-id="9156f-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9156f-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9156f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="9156f-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="9156f-116">See Also</span></span>

- [<span data-ttu-id="9156f-117">Microsoft. proIterateThroughCartesianProduct. Canon.</span><span class="sxs-lookup"><span data-stu-id="9156f-117">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)