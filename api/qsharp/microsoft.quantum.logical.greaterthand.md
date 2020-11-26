---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: c23d85cf513bb6d37e67260eeeb3b81b42e6771a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198023"
---
# <a name="greaterthand-function"></a><span data-ttu-id="abba5-102">GreaterThanD – funkce</span><span class="sxs-lookup"><span data-stu-id="abba5-102">GreaterThanD function</span></span>

<span data-ttu-id="abba5-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="abba5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="abba5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="abba5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="abba5-105">Vrátí hodnotu true pouze v případě, že je číslo větší než jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="abba5-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="abba5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="abba5-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="abba5-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="abba5-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="abba5-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="abba5-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="abba5-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="abba5-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="abba5-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="abba5-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="abba5-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="abba5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="abba5-112">`true` pouze v případě, že `a` je pouze striktně větší než `b` .</span><span class="sxs-lookup"><span data-stu-id="abba5-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="abba5-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="abba5-113">Remarks</span></span>

<span data-ttu-id="abba5-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="abba5-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```