---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 20414e80e08993a18331a8f0b385a1e4cc1255b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697304"
---
# <a name="greaterthand-function"></a><span data-ttu-id="8807c-102">GreaterThanD – funkce</span><span class="sxs-lookup"><span data-stu-id="8807c-102">GreaterThanD function</span></span>

<span data-ttu-id="8807c-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="8807c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="8807c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8807c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8807c-105">Vrátí hodnotu true pouze v případě, že je číslo větší než jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="8807c-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="8807c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8807c-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="8807c-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8807c-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8807c-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="8807c-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="8807c-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8807c-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8807c-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="8807c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8807c-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8807c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8807c-112">`true` pouze v případě, že `a` je pouze striktně větší než `b` .</span><span class="sxs-lookup"><span data-stu-id="8807c-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8807c-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="8807c-113">Remarks</span></span>

<span data-ttu-id="8807c-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="8807c-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```