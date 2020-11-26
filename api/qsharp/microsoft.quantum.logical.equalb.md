---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: b566f5ba8548eadeecf63a1e91956d936e7e9a20
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198465"
---
# <a name="equalb-function"></a><span data-ttu-id="5c34f-102">EqualB – funkce</span><span class="sxs-lookup"><span data-stu-id="5c34f-102">EqualB function</span></span>

<span data-ttu-id="5c34f-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5c34f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5c34f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5c34f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5c34f-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="5c34f-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="5c34f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5c34f-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="5c34f-107">Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5c34f-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5c34f-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="5c34f-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="5c34f-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5c34f-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5c34f-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="5c34f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5c34f-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5c34f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5c34f-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="5c34f-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c34f-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5c34f-113">Remarks</span></span>

<span data-ttu-id="5c34f-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="5c34f-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```