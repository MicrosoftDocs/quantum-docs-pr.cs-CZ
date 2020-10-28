---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 292599c18d2aac44cef8f0eecca38eb1fbe22061
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708434"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="2b1bb-102">GreaterThanOrEqualI – funkce</span><span class="sxs-lookup"><span data-stu-id="2b1bb-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="2b1bb-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2b1bb-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2b1bb-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b1bb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b1bb-105">Vrátí hodnotu true pouze v případě, že je číslo větší nebo rovno jinému číslu.</span><span class="sxs-lookup"><span data-stu-id="2b1bb-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="2b1bb-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2b1bb-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="2b1bb-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2b1bb-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2b1bb-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="2b1bb-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="2b1bb-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2b1bb-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2b1bb-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="2b1bb-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2b1bb-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2b1bb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2b1bb-112">`true` IF a pouze pokud `a` je větší než nebo je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="2b1bb-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b1bb-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2b1bb-113">Remarks</span></span>

<span data-ttu-id="2b1bb-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="2b1bb-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```