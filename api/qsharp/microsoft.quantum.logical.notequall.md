---
uid: Microsoft.Quantum.Logical.NotEqualL
title: NotEqualL – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: e138a8def30bc77499662ffa6bc214d0c6a38893
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197224"
---
# <a name="notequall-function"></a><span data-ttu-id="eb40e-102">NotEqualL – funkce</span><span class="sxs-lookup"><span data-stu-id="eb40e-102">NotEqualL function</span></span>

<span data-ttu-id="eb40e-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="eb40e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="eb40e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eb40e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eb40e-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="eb40e-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="eb40e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="eb40e-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="eb40e-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="eb40e-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="eb40e-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="eb40e-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="eb40e-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="eb40e-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="eb40e-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="eb40e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="eb40e-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="eb40e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="eb40e-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="eb40e-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="eb40e-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="eb40e-113">Remarks</span></span>

<span data-ttu-id="eb40e-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="eb40e-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```