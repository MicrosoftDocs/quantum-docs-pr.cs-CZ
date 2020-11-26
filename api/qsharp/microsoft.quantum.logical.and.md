---
uid: Microsoft.Quantum.Logical.And
title: And – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 279221ed785dd76e28146e4c22e70290936bf529
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198567"
---
# <a name="and-function"></a><span data-ttu-id="cdee9-102">And – funkce</span><span class="sxs-lookup"><span data-stu-id="cdee9-102">And function</span></span>

<span data-ttu-id="cdee9-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="cdee9-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="cdee9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cdee9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cdee9-105">Vrátí logickou kombinaci dvou hodnot.</span><span class="sxs-lookup"><span data-stu-id="cdee9-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="cdee9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="cdee9-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="cdee9-107">Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cdee9-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cdee9-108">První hodnota, která má být považována za.</span><span class="sxs-lookup"><span data-stu-id="cdee9-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="cdee9-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cdee9-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cdee9-110">Druhá hodnota, která má být považována za.</span><span class="sxs-lookup"><span data-stu-id="cdee9-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cdee9-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cdee9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cdee9-112">`true` pouze v případě, že `a` a `b` jsou obojí `true` .</span><span class="sxs-lookup"><span data-stu-id="cdee9-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cdee9-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="cdee9-113">Remarks</span></span>

<span data-ttu-id="cdee9-114">Na rozdíl od `and` operátoru Tato funkce nemá krátký okruh, takže oba vstupy jsou plně vyhodnoceny.</span><span class="sxs-lookup"><span data-stu-id="cdee9-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="cdee9-115">V případě chování až po krátkého okruhu jsou následující ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="cdee9-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a and b;
let x = And(a, b);
```