---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 40f059e49affbb1b5af7dc349f6ee53dfb357873
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197734"
---
# <a name="lessthand-function"></a><span data-ttu-id="6645c-102">LessThanD – funkce</span><span class="sxs-lookup"><span data-stu-id="6645c-102">LessThanD function</span></span>

<span data-ttu-id="6645c-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6645c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6645c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6645c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6645c-105">Vrátí hodnotu true pouze v případě, že je číslo menší než jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="6645c-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="6645c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6645c-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="6645c-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6645c-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6645c-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="6645c-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="6645c-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6645c-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6645c-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="6645c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6645c-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6645c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6645c-112">`true` pouze v případě, že `a` je pouze striktně menší než `b` .</span><span class="sxs-lookup"><span data-stu-id="6645c-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6645c-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="6645c-113">Remarks</span></span>

<span data-ttu-id="6645c-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="6645c-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```