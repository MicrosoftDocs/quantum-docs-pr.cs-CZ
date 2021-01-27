---
uid: Microsoft.Quantum.Logical.EqualI
title: Equals – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 87cf00ea8bb738cda30092b3d80940291beb1fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816753"
---
# <a name="equali-function"></a><span data-ttu-id="3b2e7-102">Equals – funkce</span><span class="sxs-lookup"><span data-stu-id="3b2e7-102">EqualI function</span></span>

<span data-ttu-id="3b2e7-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3b2e7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3b2e7-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3b2e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3b2e7-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="3b2e7-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3b2e7-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="3b2e7-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3b2e7-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3b2e7-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="3b2e7-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3b2e7-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3b2e7-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3b2e7-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3b2e7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3b2e7-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="3b2e7-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3b2e7-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="3b2e7-113">Remarks</span></span>

<span data-ttu-id="3b2e7-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="3b2e7-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualI(a, b);
```