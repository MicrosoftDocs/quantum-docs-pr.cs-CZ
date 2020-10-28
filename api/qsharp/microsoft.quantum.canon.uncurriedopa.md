---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698793"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="1289a-102">UncurriedOpA – funkce</span><span class="sxs-lookup"><span data-stu-id="1289a-102">UncurriedOpA function</span></span>

<span data-ttu-id="1289a-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1289a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1289a-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1289a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1289a-105">Funkce, která vrací operace, vrací novou operaci, která přijímá oba vstupy jako řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="1289a-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="1289a-106">Modifikátor `A` označuje, že operace jsou sousedící.</span><span class="sxs-lookup"><span data-stu-id="1289a-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="1289a-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="1289a-107">Input</span></span>

### <a name="curriedop--t---u--unit-adj"></a><span data-ttu-id="1289a-108">curriedOp: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="1289a-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1289a-109">Funkce, která vrací operace.</span><span class="sxs-lookup"><span data-stu-id="1289a-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-adj"></a><span data-ttu-id="1289a-110">Výstup: (t, ' U) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="1289a-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1289a-111">Nová operace `op` , která `op(t, u)` je ekvivalentem `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="1289a-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1289a-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="1289a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1289a-113">'S</span><span class="sxs-lookup"><span data-stu-id="1289a-113">'T</span></span>

<span data-ttu-id="1289a-114">Typ prvního argumentu funkce curryfikované</span><span class="sxs-lookup"><span data-stu-id="1289a-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="1289a-115">U</span><span class="sxs-lookup"><span data-stu-id="1289a-115">'U</span></span>

<span data-ttu-id="1289a-116">Typ druhého argumentu funkce curryfikované</span><span class="sxs-lookup"><span data-stu-id="1289a-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="1289a-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="1289a-117">See Also</span></span>

- [<span data-ttu-id="1289a-118">Microsoft. proUncurriedOp. Canon.</span><span class="sxs-lookup"><span data-stu-id="1289a-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)