---
uid: Microsoft.Quantum.Logical.EqualL
title: EQUAL – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 395b8fedd3b3334939c2a4b5602ee19e0c6e34b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198108"
---
# <a name="equall-function"></a><span data-ttu-id="fa8aa-102">EQUAL – funkce</span><span class="sxs-lookup"><span data-stu-id="fa8aa-102">EqualL function</span></span>

<span data-ttu-id="fa8aa-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fa8aa-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fa8aa-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa8aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa8aa-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="fa8aa-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="fa8aa-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="fa8aa-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="fa8aa-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fa8aa-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fa8aa-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="fa8aa-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="fa8aa-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fa8aa-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fa8aa-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="fa8aa-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fa8aa-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fa8aa-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fa8aa-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="fa8aa-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa8aa-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fa8aa-113">Remarks</span></span>

<span data-ttu-id="fa8aa-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="fa8aa-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```