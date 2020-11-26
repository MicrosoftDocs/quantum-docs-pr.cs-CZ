---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 5536c009d6e78eac9ab2320b42aec7d2d82946eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197751"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="d1205-102">GreaterThanOrEqualL – funkce</span><span class="sxs-lookup"><span data-stu-id="d1205-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="d1205-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d1205-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d1205-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1205-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1205-105">Vrátí hodnotu true pouze v případě, že je číslo větší nebo rovno jinému číslu.</span><span class="sxs-lookup"><span data-stu-id="d1205-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="d1205-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d1205-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="d1205-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d1205-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d1205-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="d1205-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="d1205-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d1205-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d1205-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="d1205-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d1205-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d1205-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d1205-112">`true` IF a pouze pokud `a` je větší než nebo je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="d1205-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d1205-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d1205-113">Remarks</span></span>

<span data-ttu-id="d1205-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="d1205-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```