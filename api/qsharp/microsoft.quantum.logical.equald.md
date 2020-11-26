---
uid: Microsoft.Quantum.Logical.EqualD
title: EQUAL – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d6731b293ba402f5cd43591d3c2bcd258e8ebe32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198142"
---
# <a name="equald-function"></a><span data-ttu-id="34433-102">EQUAL – funkce</span><span class="sxs-lookup"><span data-stu-id="34433-102">EqualD function</span></span>

<span data-ttu-id="34433-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="34433-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="34433-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34433-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34433-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="34433-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="34433-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="34433-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="34433-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="34433-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="34433-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="34433-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="34433-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="34433-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="34433-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="34433-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="34433-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="34433-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="34433-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="34433-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="34433-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="34433-113">Remarks</span></span>

<span data-ttu-id="34433-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="34433-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```