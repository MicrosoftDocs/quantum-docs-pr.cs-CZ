---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 0c9fa353b549d3c137beac3bcc3cfb0e742f6d07
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197802"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="7143a-102">GreaterThanOrEqualD – funkce</span><span class="sxs-lookup"><span data-stu-id="7143a-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="7143a-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7143a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7143a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7143a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7143a-105">Vrátí hodnotu true pouze v případě, že je číslo větší nebo rovno jinému číslu.</span><span class="sxs-lookup"><span data-stu-id="7143a-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="7143a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="7143a-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="7143a-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7143a-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7143a-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="7143a-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="7143a-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7143a-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7143a-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="7143a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7143a-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7143a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7143a-112">`true` IF a pouze pokud `a` je větší než nebo je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="7143a-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7143a-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="7143a-113">Remarks</span></span>

<span data-ttu-id="7143a-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="7143a-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```