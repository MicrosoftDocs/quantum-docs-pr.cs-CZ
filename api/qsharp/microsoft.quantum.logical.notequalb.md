---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: d5a9819bf3baa7c914487277fef308abbc8d25bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697256"
---
# <a name="notequalb-function"></a><span data-ttu-id="28575-102">NotEqualB – funkce</span><span class="sxs-lookup"><span data-stu-id="28575-102">NotEqualB function</span></span>

<span data-ttu-id="28575-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="28575-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="28575-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="28575-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="28575-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="28575-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="28575-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="28575-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="28575-107">Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="28575-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="28575-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="28575-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="28575-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="28575-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="28575-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="28575-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="28575-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="28575-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="28575-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="28575-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="28575-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="28575-113">Remarks</span></span>

<span data-ttu-id="28575-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="28575-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```