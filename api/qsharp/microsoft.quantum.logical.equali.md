---
uid: Microsoft.Quantum.Logical.EqualI
title: Equals – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 6b805e76217e033cb0135cf85bd8f37a3eb8636a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697317"
---
# <a name="equali-function"></a><span data-ttu-id="155fa-102">Equals – funkce</span><span class="sxs-lookup"><span data-stu-id="155fa-102">EqualI function</span></span>

<span data-ttu-id="155fa-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="155fa-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="155fa-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="155fa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="155fa-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="155fa-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="155fa-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="155fa-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="155fa-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="155fa-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="155fa-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="155fa-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="155fa-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="155fa-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="155fa-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="155fa-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="155fa-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="155fa-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="155fa-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="155fa-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="155fa-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="155fa-113">Remarks</span></span>

<span data-ttu-id="155fa-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="155fa-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualI(a, b);
```