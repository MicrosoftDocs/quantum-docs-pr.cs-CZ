---
uid: Microsoft.Quantum.Logical.Or
title: Or – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 4a29b7684b28b904b43ccceb8e63280999690349
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848463"
---
# <a name="or-function"></a><span data-ttu-id="d9626-102">Or – funkce</span><span class="sxs-lookup"><span data-stu-id="d9626-102">Or function</span></span>

<span data-ttu-id="d9626-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d9626-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d9626-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9626-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d9626-105">Vrátí logickou disjunkci dvou hodnot.</span><span class="sxs-lookup"><span data-stu-id="d9626-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="d9626-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d9626-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="d9626-107">Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d9626-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d9626-108">První hodnota, která má být považována za.</span><span class="sxs-lookup"><span data-stu-id="d9626-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="d9626-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d9626-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d9626-110">Druhá hodnota, která má být považována za.</span><span class="sxs-lookup"><span data-stu-id="d9626-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d9626-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d9626-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d9626-112">`true` pouze v případě, že `a` `b` jsou nebo `true` .</span><span class="sxs-lookup"><span data-stu-id="d9626-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9626-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d9626-113">Remarks</span></span>

<span data-ttu-id="d9626-114">Na rozdíl od `or` operátoru Tato funkce nemá krátký okruh, takže oba vstupy jsou plně vyhodnoceny.</span><span class="sxs-lookup"><span data-stu-id="d9626-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="d9626-115">V případě chování až po krátkého okruhu jsou následující ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="d9626-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a or b;
let x = Or(a, b);
```