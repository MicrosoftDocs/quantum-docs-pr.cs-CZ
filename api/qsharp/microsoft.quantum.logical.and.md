---
uid: Microsoft.Quantum.Logical.And
title: And – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 6c405bdb4182cc7f32bd04952dec25a974c03445
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849226"
---
# <a name="and-function"></a><span data-ttu-id="5ecbd-102">And – funkce</span><span class="sxs-lookup"><span data-stu-id="5ecbd-102">And function</span></span>

<span data-ttu-id="5ecbd-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5ecbd-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5ecbd-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5ecbd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5ecbd-105">Vrátí logickou kombinaci dvou hodnot.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="5ecbd-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5ecbd-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="5ecbd-107">Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5ecbd-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5ecbd-108">První hodnota, která má být považována za.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="5ecbd-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5ecbd-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5ecbd-110">Druhá hodnota, která má být považována za.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5ecbd-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5ecbd-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5ecbd-112">`true` pouze v případě, že `a` a `b` jsou obojí `true` .</span><span class="sxs-lookup"><span data-stu-id="5ecbd-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5ecbd-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5ecbd-113">Remarks</span></span>

<span data-ttu-id="5ecbd-114">Na rozdíl od `and` operátoru Tato funkce nemá krátký okruh, takže oba vstupy jsou plně vyhodnoceny.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="5ecbd-115">V případě chování až po krátkého okruhu jsou následující ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="5ecbd-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a and b;
let x = And(a, b);
```