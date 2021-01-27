---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 703b782efe9daccd4f6a339481d49ae9232123f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849124"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="901ab-102">LessThanOrEqualD – funkce</span><span class="sxs-lookup"><span data-stu-id="901ab-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="901ab-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="901ab-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="901ab-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="901ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="901ab-105">Vrátí hodnotu true pouze v případě, že je číslo menší nebo rovno jinému číslu.</span><span class="sxs-lookup"><span data-stu-id="901ab-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="901ab-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="901ab-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="901ab-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="901ab-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="901ab-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="901ab-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="901ab-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="901ab-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="901ab-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="901ab-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="901ab-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="901ab-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="901ab-112">`true` pouze pokud je a pouze v případě, že `a` je menší nebo rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="901ab-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="901ab-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="901ab-113">Remarks</span></span>

<span data-ttu-id="901ab-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="901ab-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```