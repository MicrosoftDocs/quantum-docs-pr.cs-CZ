---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 39601396a75d8c1b9193d4b8f34fa05466beff06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848501"
---
# <a name="notequalr-function"></a><span data-ttu-id="6fd4b-102">NotEqualR – funkce</span><span class="sxs-lookup"><span data-stu-id="6fd4b-102">NotEqualR function</span></span>

<span data-ttu-id="6fd4b-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6fd4b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6fd4b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6fd4b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6fd4b-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="6fd4b-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="6fd4b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6fd4b-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="6fd4b-107">Odpověď: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="6fd4b-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="6fd4b-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="6fd4b-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="6fd4b-109">b: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="6fd4b-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="6fd4b-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="6fd4b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6fd4b-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6fd4b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6fd4b-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="6fd4b-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6fd4b-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="6fd4b-113">Remarks</span></span>

<span data-ttu-id="6fd4b-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="6fd4b-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualR(a, b);
```