---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 86fc8e927c292a2ea814ed80a33de42bffdb96b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815944"
---
# <a name="greaterthani-function"></a><span data-ttu-id="7a968-102">GreaterThanI – funkce</span><span class="sxs-lookup"><span data-stu-id="7a968-102">GreaterThanI function</span></span>

<span data-ttu-id="7a968-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7a968-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7a968-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7a968-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7a968-105">Vrátí hodnotu true pouze v případě, že je číslo větší než jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="7a968-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="7a968-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="7a968-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="7a968-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a968-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a968-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="7a968-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="7a968-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a968-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a968-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="7a968-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7a968-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7a968-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7a968-112">`true` pouze v případě, že `a` je pouze striktně větší než `b` .</span><span class="sxs-lookup"><span data-stu-id="7a968-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7a968-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="7a968-113">Remarks</span></span>

<span data-ttu-id="7a968-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="7a968-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanI(a, b);
```