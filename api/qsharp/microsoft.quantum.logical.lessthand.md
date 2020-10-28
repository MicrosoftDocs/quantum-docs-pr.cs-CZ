---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 8cd274d5e299df2f556006baf7457d54aebcd071
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708433"
---
# <a name="lessthand-function"></a><span data-ttu-id="51e04-102">LessThanD – funkce</span><span class="sxs-lookup"><span data-stu-id="51e04-102">LessThanD function</span></span>

<span data-ttu-id="51e04-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="51e04-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="51e04-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="51e04-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="51e04-105">Vrátí hodnotu true pouze v případě, že je číslo menší než jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="51e04-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="51e04-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="51e04-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="51e04-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="51e04-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="51e04-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="51e04-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="51e04-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="51e04-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="51e04-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="51e04-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="51e04-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="51e04-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="51e04-112">`true` pouze v případě, že `a` je pouze striktně menší než `b` .</span><span class="sxs-lookup"><span data-stu-id="51e04-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="51e04-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="51e04-113">Remarks</span></span>

<span data-ttu-id="51e04-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="51e04-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```