---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dd21fcc1d0d73bd210303bfbf4f336386b912107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708427"
---
# <a name="notequald-function"></a><span data-ttu-id="13e57-102">NotEqualD – funkce</span><span class="sxs-lookup"><span data-stu-id="13e57-102">NotEqualD function</span></span>

<span data-ttu-id="13e57-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="13e57-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="13e57-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="13e57-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="13e57-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="13e57-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="13e57-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="13e57-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="13e57-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="13e57-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="13e57-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="13e57-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="13e57-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="13e57-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="13e57-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="13e57-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="13e57-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="13e57-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="13e57-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="13e57-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="13e57-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="13e57-113">Remarks</span></span>

<span data-ttu-id="13e57-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="13e57-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```