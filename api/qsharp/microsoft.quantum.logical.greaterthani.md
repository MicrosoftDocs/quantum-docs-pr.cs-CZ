---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: ffd00d8086654a2d783a351fe254fb2ee35b9184
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697297"
---
# <a name="greaterthani-function"></a><span data-ttu-id="9e732-102">GreaterThanI – funkce</span><span class="sxs-lookup"><span data-stu-id="9e732-102">GreaterThanI function</span></span>

<span data-ttu-id="9e732-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="9e732-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="9e732-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9e732-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9e732-105">Vrátí hodnotu true pouze v případě, že je číslo větší než jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="9e732-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="9e732-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="9e732-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="9e732-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9e732-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9e732-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="9e732-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="9e732-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9e732-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9e732-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="9e732-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9e732-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9e732-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9e732-112">`true` pouze v případě, že `a` je pouze striktně větší než `b` .</span><span class="sxs-lookup"><span data-stu-id="9e732-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9e732-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="9e732-113">Remarks</span></span>

<span data-ttu-id="9e732-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="9e732-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```