---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 35be5425fcd76eae9e0a6fde6a689a5db00da52f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204585"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="0d09e-102">UncurriedOpC – funkce</span><span class="sxs-lookup"><span data-stu-id="0d09e-102">UncurriedOpC function</span></span>

<span data-ttu-id="0d09e-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0d09e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0d09e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0d09e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0d09e-105">Funkce, která vrací operace, vrací novou operaci, která přijímá oba vstupy jako řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="0d09e-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="0d09e-106">Modifikátor `C` označuje, že operace lze řídit.</span><span class="sxs-lookup"><span data-stu-id="0d09e-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="0d09e-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="0d09e-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="0d09e-108">curriedOp: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="0d09e-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="0d09e-109">Funkce, která vrací operace.</span><span class="sxs-lookup"><span data-stu-id="0d09e-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-ctl"></a><span data-ttu-id="0d09e-110">Výstup: (t, ' U) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="0d09e-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="0d09e-111">Nová operace `op` , která `op(t, u)` je ekvivalentem `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="0d09e-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0d09e-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="0d09e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0d09e-113">'S</span><span class="sxs-lookup"><span data-stu-id="0d09e-113">'T</span></span>

<span data-ttu-id="0d09e-114">Typ prvního argumentu funkce curryfikované</span><span class="sxs-lookup"><span data-stu-id="0d09e-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="0d09e-115">U</span><span class="sxs-lookup"><span data-stu-id="0d09e-115">'U</span></span>

<span data-ttu-id="0d09e-116">Typ druhého argumentu funkce curryfikované</span><span class="sxs-lookup"><span data-stu-id="0d09e-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d09e-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="0d09e-117">See Also</span></span>

- [<span data-ttu-id="0d09e-118">Microsoft. proUncurriedOp. Canon.</span><span class="sxs-lookup"><span data-stu-id="0d09e-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)