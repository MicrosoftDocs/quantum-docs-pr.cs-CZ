---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 910d8a3006a2f217888b791e479e10f9f1a6965e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840040"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="8ae74-102">UncurriedOpCA – funkce</span><span class="sxs-lookup"><span data-stu-id="8ae74-102">UncurriedOpCA function</span></span>

<span data-ttu-id="8ae74-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8ae74-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8ae74-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ae74-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ae74-105">Funkce, která vrací operace, vrací novou operaci, která přijímá oba vstupy jako řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="8ae74-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="8ae74-106">Modifikátor `CA` označuje, že operace lze řídit a přiléhající.</span><span class="sxs-lookup"><span data-stu-id="8ae74-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="8ae74-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="8ae74-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj--ctl"></a><span data-ttu-id="8ae74-108">curriedOp: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="8ae74-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="8ae74-109">Funkce, která vrací operace.</span><span class="sxs-lookup"><span data-stu-id="8ae74-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj--ctl"></a><span data-ttu-id="8ae74-110">Výstup: (t, ' U) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="8ae74-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="8ae74-111">Nová operace `op` , která `op(t, u)` je ekvivalentem `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="8ae74-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8ae74-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8ae74-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8ae74-113">'S</span><span class="sxs-lookup"><span data-stu-id="8ae74-113">'T</span></span>

<span data-ttu-id="8ae74-114">Typ prvního argumentu funkce curryfikované</span><span class="sxs-lookup"><span data-stu-id="8ae74-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="8ae74-115">U</span><span class="sxs-lookup"><span data-stu-id="8ae74-115">'U</span></span>

<span data-ttu-id="8ae74-116">Typ druhého argumentu funkce curryfikované</span><span class="sxs-lookup"><span data-stu-id="8ae74-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ae74-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="8ae74-117">See Also</span></span>

- [<span data-ttu-id="8ae74-118">Microsoft. proUncurriedOp. Canon.</span><span class="sxs-lookup"><span data-stu-id="8ae74-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)