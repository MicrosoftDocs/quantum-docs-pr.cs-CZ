---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 2322ae4dd6025108d322d29770f42953213aa025
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197597"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="c2352-102">LessThanOrEqualL – funkce</span><span class="sxs-lookup"><span data-stu-id="c2352-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="c2352-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c2352-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c2352-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c2352-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c2352-105">Vrátí hodnotu true pouze v případě, že je číslo menší nebo rovno jinému číslu.</span><span class="sxs-lookup"><span data-stu-id="c2352-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="c2352-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c2352-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="c2352-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c2352-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c2352-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="c2352-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="c2352-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c2352-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c2352-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="c2352-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c2352-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c2352-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c2352-112">`true` pouze pokud je a pouze v případě, že `a` je menší nebo rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="c2352-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c2352-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c2352-113">Remarks</span></span>

<span data-ttu-id="c2352-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="c2352-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```