---
uid: Microsoft.Quantum.Logical.EqualR
title: EQUAL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 9ce29f2868f092001a3dca23a2913a3963ac70fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815978"
---
# <a name="equalr-function"></a><span data-ttu-id="f621f-102">EQUAL – funkce</span><span class="sxs-lookup"><span data-stu-id="f621f-102">EqualR function</span></span>

<span data-ttu-id="f621f-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f621f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f621f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f621f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f621f-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="f621f-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="f621f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f621f-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="f621f-107">Odpověď: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="f621f-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="f621f-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="f621f-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="f621f-109">b: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="f621f-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="f621f-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="f621f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f621f-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f621f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f621f-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="f621f-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f621f-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f621f-113">Remarks</span></span>

<span data-ttu-id="f621f-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="f621f-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualR(a, b);
```