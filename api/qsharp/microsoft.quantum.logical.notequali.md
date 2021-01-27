---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f88ae08f45c284f65151419c214705c74c3fadac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814508"
---
# <a name="notequali-function"></a><span data-ttu-id="a72f0-102">NotEqualI – funkce</span><span class="sxs-lookup"><span data-stu-id="a72f0-102">NotEqualI function</span></span>

<span data-ttu-id="a72f0-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a72f0-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a72f0-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a72f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a72f0-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="a72f0-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="a72f0-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a72f0-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="a72f0-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a72f0-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a72f0-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="a72f0-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="a72f0-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a72f0-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a72f0-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="a72f0-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a72f0-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a72f0-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a72f0-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="a72f0-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a72f0-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a72f0-113">Remarks</span></span>

<span data-ttu-id="a72f0-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="a72f0-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualI(a, b);
```