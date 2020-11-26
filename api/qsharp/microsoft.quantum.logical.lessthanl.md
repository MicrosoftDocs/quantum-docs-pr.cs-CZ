---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 9a0678569596ac188c87c3944f3759783fcc77ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197717"
---
# <a name="lessthanl-function"></a><span data-ttu-id="2c928-102">LessThanL – funkce</span><span class="sxs-lookup"><span data-stu-id="2c928-102">LessThanL function</span></span>

<span data-ttu-id="2c928-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2c928-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2c928-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2c928-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2c928-105">Vrátí hodnotu true pouze v případě, že je číslo menší než jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="2c928-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="2c928-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2c928-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="2c928-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2c928-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2c928-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="2c928-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="2c928-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2c928-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2c928-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="2c928-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2c928-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2c928-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2c928-112">`true` pouze v případě, že `a` je pouze striktně menší než `b` .</span><span class="sxs-lookup"><span data-stu-id="2c928-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2c928-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2c928-113">Remarks</span></span>

<span data-ttu-id="2c928-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="2c928-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```