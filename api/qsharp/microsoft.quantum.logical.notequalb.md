---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 9f362b9e08f8a798bf7f7d9c323fee6576dccd9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814425"
---
# <a name="notequalb-function"></a><span data-ttu-id="5128d-102">NotEqualB – funkce</span><span class="sxs-lookup"><span data-stu-id="5128d-102">NotEqualB function</span></span>

<span data-ttu-id="5128d-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5128d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5128d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5128d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5128d-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="5128d-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="5128d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5128d-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="5128d-107">Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5128d-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5128d-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="5128d-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="5128d-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5128d-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5128d-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="5128d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5128d-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5128d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5128d-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="5128d-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5128d-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5128d-113">Remarks</span></span>

<span data-ttu-id="5128d-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="5128d-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualB(a, b);
```