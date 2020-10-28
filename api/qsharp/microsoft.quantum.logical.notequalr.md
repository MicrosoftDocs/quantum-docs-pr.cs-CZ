---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697244"
---
# <a name="notequalr-function"></a><span data-ttu-id="d9f7d-102">NotEqualR – funkce</span><span class="sxs-lookup"><span data-stu-id="d9f7d-102">NotEqualR function</span></span>

<span data-ttu-id="d9f7d-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d9f7d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d9f7d-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d9f7d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d9f7d-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="d9f7d-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="d9f7d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d9f7d-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="d9f7d-107">Odpověď: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="d9f7d-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="d9f7d-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="d9f7d-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="d9f7d-109">b: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="d9f7d-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="d9f7d-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="d9f7d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d9f7d-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d9f7d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d9f7d-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="d9f7d-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9f7d-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d9f7d-113">Remarks</span></span>

<span data-ttu-id="d9f7d-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="d9f7d-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```