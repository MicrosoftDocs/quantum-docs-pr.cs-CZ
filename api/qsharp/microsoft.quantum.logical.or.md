---
uid: Microsoft.Quantum.Logical.Or
title: Or – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 98a416229386461b241d087b7ae95f078f8be70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706513"
---
# <a name="or-function"></a><span data-ttu-id="bd1cc-102">Or – funkce</span><span class="sxs-lookup"><span data-stu-id="bd1cc-102">Or function</span></span>

<span data-ttu-id="bd1cc-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="bd1cc-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="bd1cc-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bd1cc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bd1cc-105">Vrátí logickou disjunkci dvou hodnot.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="bd1cc-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="bd1cc-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="bd1cc-107">Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bd1cc-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bd1cc-108">První hodnota, která má být považována za.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="bd1cc-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bd1cc-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bd1cc-110">Druhá hodnota, která má být považována za.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="bd1cc-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bd1cc-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bd1cc-112">`true` pouze v případě, že `a` `b` jsou nebo `true` .</span><span class="sxs-lookup"><span data-stu-id="bd1cc-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd1cc-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="bd1cc-113">Remarks</span></span>

<span data-ttu-id="bd1cc-114">Na rozdíl od `or` operátoru Tato funkce nemá krátký okruh, takže oba vstupy jsou plně vyhodnoceny.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="bd1cc-115">V případě chování až po krátkého okruhu jsou následující ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="bd1cc-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a or b;
let x = Or(a, b);
```