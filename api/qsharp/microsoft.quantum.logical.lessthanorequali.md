---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: b2974c9bc84d0b4366767f47682ab542f85063e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197562"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="6a724-102">LessThanOrEqualI – funkce</span><span class="sxs-lookup"><span data-stu-id="6a724-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="6a724-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6a724-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6a724-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6a724-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6a724-105">Vrátí hodnotu true pouze v případě, že je číslo menší nebo rovno jinému číslu.</span><span class="sxs-lookup"><span data-stu-id="6a724-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="6a724-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6a724-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="6a724-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6a724-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6a724-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="6a724-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="6a724-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6a724-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6a724-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="6a724-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6a724-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6a724-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6a724-112">`true` pouze pokud je a pouze v případě, že `a` je menší nebo rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="6a724-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6a724-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="6a724-113">Remarks</span></span>

<span data-ttu-id="6a724-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="6a724-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```