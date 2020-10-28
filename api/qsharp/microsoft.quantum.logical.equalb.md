---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 91ab51180018a9b95a2f9010477c0a24f3a54617
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707049"
---
# <a name="equalb-function"></a><span data-ttu-id="11dfc-102">EqualB – funkce</span><span class="sxs-lookup"><span data-stu-id="11dfc-102">EqualB function</span></span>

<span data-ttu-id="11dfc-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="11dfc-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="11dfc-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="11dfc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="11dfc-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="11dfc-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="11dfc-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="11dfc-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="11dfc-107">Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="11dfc-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="11dfc-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="11dfc-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="11dfc-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="11dfc-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="11dfc-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="11dfc-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="11dfc-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="11dfc-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="11dfc-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="11dfc-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="11dfc-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="11dfc-113">Remarks</span></span>

<span data-ttu-id="11dfc-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="11dfc-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```