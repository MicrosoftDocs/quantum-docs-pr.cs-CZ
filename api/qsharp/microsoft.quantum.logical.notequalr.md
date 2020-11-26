---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4ac6cf4b220fa42c8eb946d6fbcad4cdb191afcd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197190"
---
# <a name="notequalr-function"></a><span data-ttu-id="41efa-102">NotEqualR – funkce</span><span class="sxs-lookup"><span data-stu-id="41efa-102">NotEqualR function</span></span>

<span data-ttu-id="41efa-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="41efa-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="41efa-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41efa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41efa-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="41efa-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="41efa-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="41efa-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="41efa-107">Odpověď: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="41efa-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="41efa-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="41efa-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="41efa-109">b: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="41efa-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="41efa-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="41efa-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="41efa-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="41efa-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="41efa-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="41efa-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="41efa-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="41efa-113">Remarks</span></span>

<span data-ttu-id="41efa-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="41efa-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```