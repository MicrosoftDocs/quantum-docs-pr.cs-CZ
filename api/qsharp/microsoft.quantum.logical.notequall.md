---
uid: Microsoft.Quantum.Logical.NotEqualL
title: NotEqualL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f1d36c284293519e75e6c30ac64679c7bdf4609c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697248"
---
# <a name="notequall-function"></a><span data-ttu-id="826a8-102">NotEqualL – funkce</span><span class="sxs-lookup"><span data-stu-id="826a8-102">NotEqualL function</span></span>

<span data-ttu-id="826a8-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="826a8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="826a8-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="826a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="826a8-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="826a8-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="826a8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="826a8-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="826a8-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="826a8-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="826a8-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="826a8-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="826a8-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="826a8-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="826a8-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="826a8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="826a8-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="826a8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="826a8-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="826a8-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="826a8-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="826a8-113">Remarks</span></span>

<span data-ttu-id="826a8-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="826a8-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```