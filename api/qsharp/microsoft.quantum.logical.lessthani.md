---
uid: Microsoft.Quantum.Logical.LessThanI
title: LessThanI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 204e62a87d2b3d0070946985030d038ead686457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708428"
---
# <a name="lessthani-function"></a><span data-ttu-id="12746-102">LessThanI – funkce</span><span class="sxs-lookup"><span data-stu-id="12746-102">LessThanI function</span></span>

<span data-ttu-id="12746-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="12746-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="12746-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="12746-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="12746-105">Vrátí hodnotu true pouze v případě, že je číslo menší než jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="12746-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="12746-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="12746-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="12746-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="12746-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="12746-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="12746-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="12746-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="12746-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="12746-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="12746-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="12746-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="12746-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="12746-112">`true` pouze v případě, že `a` je pouze striktně menší než `b` .</span><span class="sxs-lookup"><span data-stu-id="12746-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="12746-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="12746-113">Remarks</span></span>

<span data-ttu-id="12746-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="12746-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```