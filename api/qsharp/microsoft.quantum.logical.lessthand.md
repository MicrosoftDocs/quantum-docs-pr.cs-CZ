---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 7135ed4b3414d143f5020496ae524bf89980a8a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849163"
---
# <a name="lessthand-function"></a><span data-ttu-id="93cf1-102">LessThanD – funkce</span><span class="sxs-lookup"><span data-stu-id="93cf1-102">LessThanD function</span></span>

<span data-ttu-id="93cf1-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="93cf1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="93cf1-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="93cf1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="93cf1-105">Vrátí hodnotu true pouze v případě, že je číslo menší než jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="93cf1-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="93cf1-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="93cf1-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="93cf1-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="93cf1-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="93cf1-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="93cf1-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="93cf1-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="93cf1-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="93cf1-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="93cf1-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="93cf1-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="93cf1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="93cf1-112">`true` pouze v případě, že `a` je pouze striktně menší než `b` .</span><span class="sxs-lookup"><span data-stu-id="93cf1-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="93cf1-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="93cf1-113">Remarks</span></span>

<span data-ttu-id="93cf1-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="93cf1-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanD(a, b);
```