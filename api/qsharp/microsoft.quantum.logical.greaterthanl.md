---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 676defa7824e53578504c559c6d8f24b2ffc1a88
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697697"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="d475b-102">GreaterThanL – funkce</span><span class="sxs-lookup"><span data-stu-id="d475b-102">GreaterThanL function</span></span>

<span data-ttu-id="d475b-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d475b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d475b-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d475b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d475b-105">Vrátí hodnotu true pouze v případě, že je číslo větší než jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="d475b-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="d475b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d475b-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="d475b-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d475b-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d475b-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="d475b-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="d475b-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d475b-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d475b-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="d475b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d475b-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d475b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d475b-112">`true` pouze v případě, že `a` je pouze striktně větší než `b` .</span><span class="sxs-lookup"><span data-stu-id="d475b-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d475b-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d475b-113">Remarks</span></span>

<span data-ttu-id="d475b-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="d475b-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```