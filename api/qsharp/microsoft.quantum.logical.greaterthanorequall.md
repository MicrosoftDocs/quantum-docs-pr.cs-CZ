---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: a59a9eca2941a44a70ec5a379b146ac459390bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708068"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="b2db3-102">GreaterThanOrEqualL – funkce</span><span class="sxs-lookup"><span data-stu-id="b2db3-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="b2db3-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b2db3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b2db3-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2db3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2db3-105">Vrátí hodnotu true pouze v případě, že je číslo větší nebo rovno jinému číslu.</span><span class="sxs-lookup"><span data-stu-id="b2db3-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="b2db3-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="b2db3-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="b2db3-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b2db3-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b2db3-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="b2db3-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="b2db3-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b2db3-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b2db3-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="b2db3-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b2db3-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b2db3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b2db3-112">`true` IF a pouze pokud `a` je větší než nebo je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="b2db3-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b2db3-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b2db3-113">Remarks</span></span>

<span data-ttu-id="b2db3-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="b2db3-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```