---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 1de3fdb0fa53fef9cbf4b9ee9b6a1c54865bd093
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849113"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="25a8a-102">LessThanOrEqualL – funkce</span><span class="sxs-lookup"><span data-stu-id="25a8a-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="25a8a-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="25a8a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="25a8a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="25a8a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="25a8a-105">Vrátí hodnotu true pouze v případě, že je číslo menší nebo rovno jinému číslu.</span><span class="sxs-lookup"><span data-stu-id="25a8a-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="25a8a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="25a8a-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="25a8a-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="25a8a-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="25a8a-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="25a8a-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="25a8a-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="25a8a-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="25a8a-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="25a8a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="25a8a-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="25a8a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="25a8a-112">`true` pouze pokud je a pouze v případě, že `a` je menší nebo rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="25a8a-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="25a8a-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="25a8a-113">Remarks</span></span>

<span data-ttu-id="25a8a-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="25a8a-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```