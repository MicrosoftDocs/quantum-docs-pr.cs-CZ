---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 5e1b2adab36b7937c83ea912b8a9cb148b626ee5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197972"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="5fa20-102">GreaterThanL – funkce</span><span class="sxs-lookup"><span data-stu-id="5fa20-102">GreaterThanL function</span></span>

<span data-ttu-id="5fa20-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5fa20-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5fa20-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5fa20-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5fa20-105">Vrátí hodnotu true pouze v případě, že je číslo větší než jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="5fa20-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="5fa20-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5fa20-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="5fa20-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5fa20-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5fa20-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="5fa20-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="5fa20-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5fa20-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5fa20-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="5fa20-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5fa20-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5fa20-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5fa20-112">`true` pouze v případě, že `a` je pouze striktně větší než `b` .</span><span class="sxs-lookup"><span data-stu-id="5fa20-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5fa20-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5fa20-113">Remarks</span></span>

<span data-ttu-id="5fa20-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="5fa20-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```