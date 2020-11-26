---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4599d7125dbc67547af454183f620e8d84f2caf7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197241"
---
# <a name="notequald-function"></a><span data-ttu-id="4e662-102">NotEqualD – funkce</span><span class="sxs-lookup"><span data-stu-id="4e662-102">NotEqualD function</span></span>

<span data-ttu-id="4e662-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4e662-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4e662-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4e662-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4e662-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="4e662-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="4e662-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4e662-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="4e662-107">Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4e662-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4e662-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="4e662-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="4e662-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4e662-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4e662-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="4e662-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4e662-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4e662-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4e662-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="4e662-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e662-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4e662-113">Remarks</span></span>

<span data-ttu-id="4e662-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="4e662-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```