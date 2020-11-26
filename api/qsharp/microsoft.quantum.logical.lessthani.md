---
uid: Microsoft.Quantum.Logical.LessThanI
title: LessThanI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 5d5b17c8481ccf58b8e4fc4bb958e0adbf6d8f00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197768"
---
# <a name="lessthani-function"></a><span data-ttu-id="c70ff-102">LessThanI – funkce</span><span class="sxs-lookup"><span data-stu-id="c70ff-102">LessThanI function</span></span>

<span data-ttu-id="c70ff-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c70ff-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c70ff-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c70ff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c70ff-105">Vrátí hodnotu true pouze v případě, že je číslo menší než jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="c70ff-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="c70ff-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c70ff-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="c70ff-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c70ff-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c70ff-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="c70ff-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="c70ff-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c70ff-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c70ff-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="c70ff-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c70ff-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c70ff-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c70ff-112">`true` pouze v případě, že `a` je pouze striktně menší než `b` .</span><span class="sxs-lookup"><span data-stu-id="c70ff-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c70ff-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c70ff-113">Remarks</span></span>

<span data-ttu-id="c70ff-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="c70ff-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```