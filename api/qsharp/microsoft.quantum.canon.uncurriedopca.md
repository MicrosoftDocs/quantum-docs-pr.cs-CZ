---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698789"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="8ddf1-102">UncurriedOpCA – funkce</span><span class="sxs-lookup"><span data-stu-id="8ddf1-102">UncurriedOpCA function</span></span>

<span data-ttu-id="8ddf1-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8ddf1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8ddf1-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8ddf1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8ddf1-105">Funkce, která vrací operace, vrací novou operaci, která přijímá oba vstupy jako řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="8ddf1-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="8ddf1-106">Modifikátor `CA` označuje, že operace lze řídit a přiléhající.</span><span class="sxs-lookup"><span data-stu-id="8ddf1-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="8ddf1-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="8ddf1-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl--adj"></a><span data-ttu-id="8ddf1-108">curriedOp: t-> ' U [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL a ADJ</span><span class="sxs-lookup"><span data-stu-id="8ddf1-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="8ddf1-109">Funkce, která vrací operace.</span><span class="sxs-lookup"><span data-stu-id="8ddf1-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl--adj"></a><span data-ttu-id="8ddf1-110">Výstup: (ne, ' U) [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="8ddf1-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="8ddf1-111">Nová operace `op` , která `op(t, u)` je ekvivalentem `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="8ddf1-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8ddf1-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8ddf1-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8ddf1-113">'S</span><span class="sxs-lookup"><span data-stu-id="8ddf1-113">'T</span></span>

<span data-ttu-id="8ddf1-114">Typ prvního argumentu funkce curryfikované</span><span class="sxs-lookup"><span data-stu-id="8ddf1-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="8ddf1-115">U</span><span class="sxs-lookup"><span data-stu-id="8ddf1-115">'U</span></span>

<span data-ttu-id="8ddf1-116">Typ druhého argumentu funkce curryfikované</span><span class="sxs-lookup"><span data-stu-id="8ddf1-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ddf1-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="8ddf1-117">See Also</span></span>

- [<span data-ttu-id="8ddf1-118">Microsoft. proUncurriedOp. Canon.</span><span class="sxs-lookup"><span data-stu-id="8ddf1-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)