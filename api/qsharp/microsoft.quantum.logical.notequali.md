---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dc132cbab556bd4b5d5c557ad267f1839e8039fc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197207"
---
# <a name="notequali-function"></a><span data-ttu-id="7a15e-102">NotEqualI – funkce</span><span class="sxs-lookup"><span data-stu-id="7a15e-102">NotEqualI function</span></span>

<span data-ttu-id="7a15e-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7a15e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7a15e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7a15e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7a15e-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="7a15e-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="7a15e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="7a15e-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="7a15e-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a15e-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a15e-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="7a15e-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="7a15e-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a15e-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a15e-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="7a15e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7a15e-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7a15e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7a15e-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="7a15e-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7a15e-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="7a15e-113">Remarks</span></span>

<span data-ttu-id="7a15e-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="7a15e-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```