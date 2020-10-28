---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: 332f9ea1753b539eba7b931d5b948b2a238d1abf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697265"
---
# <a name="nearlyequald-function"></a><span data-ttu-id="c5e57-102">NearlyEqualD – funkce</span><span class="sxs-lookup"><span data-stu-id="c5e57-102">NearlyEqualD function</span></span>

<span data-ttu-id="c5e57-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c5e57-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c5e57-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c5e57-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c5e57-105">Vrátí hodnotu true pouze v případě, že dva vstupy jsou téměř stejné (tj. v rámci tolerance 1E-12).</span><span class="sxs-lookup"><span data-stu-id="c5e57-105">Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).</span></span>

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="c5e57-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c5e57-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="c5e57-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c5e57-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c5e57-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="c5e57-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="c5e57-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c5e57-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c5e57-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="c5e57-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c5e57-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c5e57-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c5e57-112">`true` pouze pokud `a` je téměř rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="c5e57-112">`true` if and only if `a` is nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5e57-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c5e57-113">Remarks</span></span>

<span data-ttu-id="c5e57-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="c5e57-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```