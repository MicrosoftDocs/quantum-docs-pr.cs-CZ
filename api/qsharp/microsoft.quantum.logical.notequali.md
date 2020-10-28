---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 68e0e105a6b3742ec11e80ff92c39578a786aa85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697253"
---
# <a name="notequali-function"></a><span data-ttu-id="ac739-102">NotEqualI – funkce</span><span class="sxs-lookup"><span data-stu-id="ac739-102">NotEqualI function</span></span>

<span data-ttu-id="ac739-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ac739-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ac739-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ac739-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ac739-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="ac739-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="ac739-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ac739-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="ac739-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac739-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac739-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="ac739-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="ac739-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac739-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac739-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="ac739-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ac739-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ac739-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ac739-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="ac739-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac739-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ac739-113">Remarks</span></span>

<span data-ttu-id="ac739-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="ac739-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```