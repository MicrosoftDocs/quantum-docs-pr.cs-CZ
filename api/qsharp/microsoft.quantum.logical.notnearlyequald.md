---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: 6e4cf3ec009f55ecc6345453c080520a3af6a8ef
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848494"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="33220-102">NotNearlyEqualD – funkce</span><span class="sxs-lookup"><span data-stu-id="33220-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="33220-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="33220-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="33220-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="33220-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="33220-105">Vrátí hodnotu true pouze v případě, že dva vstupy nejsou téměř stejné (to znamená, že nejsou v rámci tolerance 1E-12).</span><span class="sxs-lookup"><span data-stu-id="33220-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="33220-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="33220-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="33220-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="33220-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="33220-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="33220-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="33220-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="33220-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="33220-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="33220-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="33220-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="33220-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="33220-112">`true` pouze pokud `a` není téměř rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="33220-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="33220-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="33220-113">Remarks</span></span>

<span data-ttu-id="33220-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="33220-114">The following are equivalent:</span></span>

```qsharp
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```