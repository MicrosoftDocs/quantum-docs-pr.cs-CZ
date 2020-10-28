---
uid: Microsoft.Quantum.Logical.EqualL
title: EQUAL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f0a2bfa866068746e9c6e249573eb61c0d08c0f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697313"
---
# <a name="equall-function"></a><span data-ttu-id="fac13-102">EQUAL – funkce</span><span class="sxs-lookup"><span data-stu-id="fac13-102">EqualL function</span></span>

<span data-ttu-id="fac13-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fac13-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fac13-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fac13-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fac13-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="fac13-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="fac13-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="fac13-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="fac13-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fac13-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fac13-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="fac13-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="fac13-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fac13-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fac13-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="fac13-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fac13-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fac13-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fac13-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="fac13-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fac13-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fac13-113">Remarks</span></span>

<span data-ttu-id="fac13-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="fac13-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```