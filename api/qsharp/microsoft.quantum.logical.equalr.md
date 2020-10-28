---
uid: Microsoft.Quantum.Logical.EqualR
title: EQUAL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 5aaa17303d75b27c3ac82cbe7d739a60016fdcb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697312"
---
# <a name="equalr-function"></a><span data-ttu-id="0dea3-102">EQUAL – funkce</span><span class="sxs-lookup"><span data-stu-id="0dea3-102">EqualR function</span></span>

<span data-ttu-id="0dea3-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0dea3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0dea3-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0dea3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0dea3-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="0dea3-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="0dea3-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="0dea3-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="0dea3-107">Odpověď: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="0dea3-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="0dea3-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="0dea3-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="0dea3-109">b: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="0dea3-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="0dea3-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="0dea3-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0dea3-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0dea3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0dea3-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="0dea3-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0dea3-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="0dea3-113">Remarks</span></span>

<span data-ttu-id="0dea3-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="0dea3-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```