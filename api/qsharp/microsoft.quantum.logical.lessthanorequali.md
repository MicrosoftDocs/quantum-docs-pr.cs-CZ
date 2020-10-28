---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: dd934fde3fae9c1a43032b4b08ac03afa72798d1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697284"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="5230a-102">LessThanOrEqualI – funkce</span><span class="sxs-lookup"><span data-stu-id="5230a-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="5230a-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5230a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5230a-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5230a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5230a-105">Vrátí hodnotu true pouze v případě, že je číslo menší nebo rovno jinému číslu.</span><span class="sxs-lookup"><span data-stu-id="5230a-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="5230a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5230a-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="5230a-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5230a-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5230a-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="5230a-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="5230a-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5230a-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5230a-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="5230a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5230a-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5230a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5230a-112">`true` pouze pokud je a pouze v případě, že `a` je menší nebo rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="5230a-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5230a-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5230a-113">Remarks</span></span>

<span data-ttu-id="5230a-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="5230a-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```