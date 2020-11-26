---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: 23229b1630982eba4485330cc2290aed733c4d86
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197139"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="16ebd-102">NotNearlyEqualD – funkce</span><span class="sxs-lookup"><span data-stu-id="16ebd-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="16ebd-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="16ebd-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="16ebd-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16ebd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="16ebd-105">Vrátí hodnotu true pouze v případě, že dva vstupy nejsou téměř stejné (to znamená, že nejsou v rámci tolerance 1E-12).</span><span class="sxs-lookup"><span data-stu-id="16ebd-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="16ebd-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="16ebd-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="16ebd-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="16ebd-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="16ebd-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="16ebd-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="16ebd-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="16ebd-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="16ebd-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="16ebd-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="16ebd-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="16ebd-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="16ebd-112">`true` pouze pokud `a` není téměř rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="16ebd-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="16ebd-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="16ebd-113">Remarks</span></span>

<span data-ttu-id="16ebd-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="16ebd-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```