---
uid: Microsoft.Quantum.Logical.EqualD
title: EQUAL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f8a24d7bfb9b4f7b8b0e1f68a94bfb341716b024
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816872"
---
# <a name="equald-function"></a><span data-ttu-id="4a96e-102">EQUAL – funkce</span><span class="sxs-lookup"><span data-stu-id="4a96e-102">EqualD function</span></span>

<span data-ttu-id="4a96e-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4a96e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4a96e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4a96e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4a96e-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="4a96e-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="4a96e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4a96e-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="4a96e-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4a96e-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4a96e-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="4a96e-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="4a96e-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4a96e-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4a96e-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="4a96e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4a96e-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4a96e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4a96e-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="4a96e-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4a96e-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4a96e-113">Remarks</span></span>

<span data-ttu-id="4a96e-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="4a96e-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualD(a, b);
```