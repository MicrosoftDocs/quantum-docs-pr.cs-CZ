---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 0435aae4a824bd19d972e9f6b331260bbe21f692
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197785"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="e9c23-102">GreaterThanOrEqualI – funkce</span><span class="sxs-lookup"><span data-stu-id="e9c23-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="e9c23-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e9c23-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e9c23-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e9c23-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e9c23-105">Vrátí hodnotu true pouze v případě, že je číslo větší nebo rovno jinému číslu.</span><span class="sxs-lookup"><span data-stu-id="e9c23-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="e9c23-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e9c23-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="e9c23-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e9c23-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e9c23-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="e9c23-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="e9c23-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e9c23-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e9c23-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="e9c23-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e9c23-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e9c23-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e9c23-112">`true` IF a pouze pokud `a` je větší než nebo je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="e9c23-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e9c23-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e9c23-113">Remarks</span></span>

<span data-ttu-id="e9c23-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="e9c23-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```