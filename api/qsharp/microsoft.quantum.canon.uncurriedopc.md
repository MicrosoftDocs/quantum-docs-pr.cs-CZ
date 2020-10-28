---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698792"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="d2d47-102">UncurriedOpC – funkce</span><span class="sxs-lookup"><span data-stu-id="d2d47-102">UncurriedOpC function</span></span>

<span data-ttu-id="d2d47-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d2d47-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d2d47-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d2d47-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d2d47-105">Funkce, která vrací operace, vrací novou operaci, která přijímá oba vstupy jako řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="d2d47-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="d2d47-106">Modifikátor `C` označuje, že operace lze řídit.</span><span class="sxs-lookup"><span data-stu-id="d2d47-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="d2d47-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="d2d47-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl"></a><span data-ttu-id="d2d47-108">curriedOp: t-> ' U [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="d2d47-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="d2d47-109">Funkce, která vrací operace.</span><span class="sxs-lookup"><span data-stu-id="d2d47-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl"></a><span data-ttu-id="d2d47-110">Výstup: (t, ' U) [=> CTL](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d2d47-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="d2d47-111">Nová operace `op` , která `op(t, u)` je ekvivalentem `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="d2d47-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d2d47-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d2d47-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d2d47-113">'S</span><span class="sxs-lookup"><span data-stu-id="d2d47-113">'T</span></span>

<span data-ttu-id="d2d47-114">Typ prvního argumentu funkce curryfikované</span><span class="sxs-lookup"><span data-stu-id="d2d47-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="d2d47-115">U</span><span class="sxs-lookup"><span data-stu-id="d2d47-115">'U</span></span>

<span data-ttu-id="d2d47-116">Typ druhého argumentu funkce curryfikované</span><span class="sxs-lookup"><span data-stu-id="d2d47-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2d47-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="d2d47-117">See Also</span></span>

- [<span data-ttu-id="d2d47-118">Microsoft. proUncurriedOp. Canon.</span><span class="sxs-lookup"><span data-stu-id="d2d47-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)