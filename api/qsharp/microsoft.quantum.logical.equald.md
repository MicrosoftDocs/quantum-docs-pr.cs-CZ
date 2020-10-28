---
uid: Microsoft.Quantum.Logical.EqualD
title: EQUAL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 024ddee785a6a907b4a39d0eccc5990b4c5d5d83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697701"
---
# <a name="equald-function"></a><span data-ttu-id="e419f-102">EQUAL – funkce</span><span class="sxs-lookup"><span data-stu-id="e419f-102">EqualD function</span></span>

<span data-ttu-id="e419f-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e419f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e419f-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e419f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e419f-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="e419f-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="e419f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e419f-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="e419f-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e419f-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e419f-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="e419f-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="e419f-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e419f-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e419f-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="e419f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e419f-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e419f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e419f-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="e419f-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e419f-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e419f-113">Remarks</span></span>

<span data-ttu-id="e419f-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="e419f-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```