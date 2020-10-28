---
uid: Microsoft.Quantum.Logical.And
title: And – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707064"
---
# <a name="and-function"></a><span data-ttu-id="fdfca-102">And – funkce</span><span class="sxs-lookup"><span data-stu-id="fdfca-102">And function</span></span>

<span data-ttu-id="fdfca-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fdfca-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fdfca-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fdfca-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fdfca-105">Vrátí logickou kombinaci dvou hodnot.</span><span class="sxs-lookup"><span data-stu-id="fdfca-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="fdfca-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="fdfca-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="fdfca-107">Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fdfca-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fdfca-108">První hodnota, která má být považována za.</span><span class="sxs-lookup"><span data-stu-id="fdfca-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="fdfca-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fdfca-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fdfca-110">Druhá hodnota, která má být považována za.</span><span class="sxs-lookup"><span data-stu-id="fdfca-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fdfca-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fdfca-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fdfca-112">`true` pouze v případě, že `a` a `b` jsou obojí `true` .</span><span class="sxs-lookup"><span data-stu-id="fdfca-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fdfca-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fdfca-113">Remarks</span></span>

<span data-ttu-id="fdfca-114">Na rozdíl od `and` operátoru Tato funkce nemá krátký okruh, takže oba vstupy jsou plně vyhodnoceny.</span><span class="sxs-lookup"><span data-stu-id="fdfca-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="fdfca-115">V případě chování až po krátkého okruhu jsou následující ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="fdfca-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a and b;
let x = And(a, b);
```