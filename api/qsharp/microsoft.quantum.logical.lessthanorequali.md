---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 9438fc05b4ccb041b087f9cfeb30ac0c8cfcabd6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815612"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="18e55-102">LessThanOrEqualI – funkce</span><span class="sxs-lookup"><span data-stu-id="18e55-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="18e55-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="18e55-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="18e55-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="18e55-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="18e55-105">Vrátí hodnotu true pouze v případě, že je číslo menší nebo rovno jinému číslu.</span><span class="sxs-lookup"><span data-stu-id="18e55-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="18e55-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="18e55-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="18e55-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="18e55-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="18e55-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="18e55-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="18e55-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="18e55-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="18e55-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="18e55-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="18e55-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="18e55-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="18e55-112">`true` pouze pokud je a pouze v případě, že `a` je menší nebo rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="18e55-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="18e55-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="18e55-113">Remarks</span></span>

<span data-ttu-id="18e55-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="18e55-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```