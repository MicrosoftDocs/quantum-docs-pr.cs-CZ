---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operace DrawRandomInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851145"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="99ba0-102">Operace DrawRandomInt</span><span class="sxs-lookup"><span data-stu-id="99ba0-102">DrawRandomInt operation</span></span>

<span data-ttu-id="99ba0-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="99ba0-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="99ba0-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="99ba0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="99ba0-105">Vykreslí náhodné celé číslo v daném rozsahu.</span><span class="sxs-lookup"><span data-stu-id="99ba0-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="99ba0-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="99ba0-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="99ba0-107">minimum: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="99ba0-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="99ba0-108">Nejmenší celé číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="99ba0-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="99ba0-109">maximum: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="99ba0-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="99ba0-110">Největší celé číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="99ba0-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="99ba0-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="99ba0-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="99ba0-112">Celé číslo v rozsahu v rozsahu od `min` do `max` s jednotnou pravděpodobností.</span><span class="sxs-lookup"><span data-stu-id="99ba0-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="99ba0-113">Příklad</span><span class="sxs-lookup"><span data-stu-id="99ba0-113">Example</span></span>

<span data-ttu-id="99ba0-114">Následující fragment Q # náhodně zavede na šestou kostku:</span><span class="sxs-lookup"><span data-stu-id="99ba0-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a><span data-ttu-id="99ba0-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="99ba0-115">Remarks</span></span>

<span data-ttu-id="99ba0-116">Dojde k chybě `max <= min` , pokud.</span><span class="sxs-lookup"><span data-stu-id="99ba0-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="99ba0-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="99ba0-117">See Also</span></span>

- [<span data-ttu-id="99ba0-118">Microsoft. DiscreteUniformDistribution.</span><span class="sxs-lookup"><span data-stu-id="99ba0-118">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)