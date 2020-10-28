---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 9d794fa94c1ccbde4030c90198fd7c7654469876
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697696"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="4d44e-102">GreaterThanOrEqualD – funkce</span><span class="sxs-lookup"><span data-stu-id="4d44e-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="4d44e-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4d44e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4d44e-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4d44e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4d44e-105">Vrátí hodnotu true pouze v případě, že je číslo větší nebo rovno jinému číslu.</span><span class="sxs-lookup"><span data-stu-id="4d44e-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="4d44e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4d44e-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="4d44e-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4d44e-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4d44e-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="4d44e-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="4d44e-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4d44e-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4d44e-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="4d44e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4d44e-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4d44e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4d44e-112">`true` IF a pouze pokud `a` je větší než nebo je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="4d44e-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4d44e-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4d44e-113">Remarks</span></span>

<span data-ttu-id="4d44e-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="4d44e-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```