---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 2a15a749f52fe814db4fa57118f69c80fa22158a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817260"
---
# <a name="equalb-function"></a><span data-ttu-id="0d1aa-102">EqualB – funkce</span><span class="sxs-lookup"><span data-stu-id="0d1aa-102">EqualB function</span></span>

<span data-ttu-id="0d1aa-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0d1aa-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0d1aa-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0d1aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0d1aa-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="0d1aa-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="0d1aa-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="0d1aa-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="0d1aa-107">Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0d1aa-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0d1aa-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="0d1aa-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="0d1aa-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0d1aa-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0d1aa-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="0d1aa-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0d1aa-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0d1aa-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0d1aa-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="0d1aa-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0d1aa-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="0d1aa-113">Remarks</span></span>

<span data-ttu-id="0d1aa-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="0d1aa-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualB(a, b);
```