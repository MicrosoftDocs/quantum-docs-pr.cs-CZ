---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 2247c1c1ae8b37b59e87c0c68b06fd1094c9003b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849201"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="4ce03-102">GreaterThanL – funkce</span><span class="sxs-lookup"><span data-stu-id="4ce03-102">GreaterThanL function</span></span>

<span data-ttu-id="4ce03-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4ce03-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4ce03-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4ce03-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4ce03-105">Vrátí hodnotu true pouze v případě, že je číslo větší než jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="4ce03-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="4ce03-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4ce03-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="4ce03-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4ce03-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4ce03-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="4ce03-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="4ce03-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4ce03-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4ce03-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="4ce03-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4ce03-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4ce03-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4ce03-112">`true` pouze v případě, že `a` je pouze striktně větší než `b` .</span><span class="sxs-lookup"><span data-stu-id="4ce03-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ce03-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4ce03-113">Remarks</span></span>

<span data-ttu-id="4ce03-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="4ce03-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanL(a, b);
```