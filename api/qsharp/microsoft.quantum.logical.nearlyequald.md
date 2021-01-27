---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: fbbf1f7a59600ecc4a0a59d1c08cd0e1310d2d20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814366"
---
# <a name="nearlyequald-function"></a><span data-ttu-id="f0049-102">NearlyEqualD – funkce</span><span class="sxs-lookup"><span data-stu-id="f0049-102">NearlyEqualD function</span></span>

<span data-ttu-id="f0049-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f0049-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f0049-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0049-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f0049-105">Vrátí hodnotu true pouze v případě, že dva vstupy jsou téměř stejné (tj. v rámci tolerance 1E-12).</span><span class="sxs-lookup"><span data-stu-id="f0049-105">Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).</span></span>

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="f0049-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f0049-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="f0049-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f0049-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f0049-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="f0049-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="f0049-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f0049-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f0049-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="f0049-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f0049-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f0049-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f0049-112">`true` pouze pokud `a` je téměř rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="f0049-112">`true` if and only if `a` is nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0049-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f0049-113">Remarks</span></span>

<span data-ttu-id="f0049-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="f0049-114">The following are equivalent:</span></span>

```qsharp
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```