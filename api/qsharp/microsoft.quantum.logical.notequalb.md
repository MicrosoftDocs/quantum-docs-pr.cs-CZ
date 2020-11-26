---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 7943411b662683df058213a9e4b8eb7c9329ff07
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197377"
---
# <a name="notequalb-function"></a><span data-ttu-id="5c517-102">NotEqualB – funkce</span><span class="sxs-lookup"><span data-stu-id="5c517-102">NotEqualB function</span></span>

<span data-ttu-id="5c517-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5c517-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5c517-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5c517-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5c517-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="5c517-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="5c517-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5c517-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="5c517-107">Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5c517-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5c517-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="5c517-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="5c517-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5c517-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5c517-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="5c517-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5c517-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5c517-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5c517-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="5c517-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c517-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5c517-113">Remarks</span></span>

<span data-ttu-id="5c517-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="5c517-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```