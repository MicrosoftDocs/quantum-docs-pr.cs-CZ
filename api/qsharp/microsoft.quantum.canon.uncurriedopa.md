---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: feb5da771ee6cb6a750fa76f9ffd8f5a3e0b5734
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840053"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="d936c-102">UncurriedOpA – funkce</span><span class="sxs-lookup"><span data-stu-id="d936c-102">UncurriedOpA function</span></span>

<span data-ttu-id="d936c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d936c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d936c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d936c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d936c-105">Funkce, která vrací operace, vrací novou operaci, která přijímá oba vstupy jako řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="d936c-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="d936c-106">Modifikátor `A` označuje, že operace jsou sousedící.</span><span class="sxs-lookup"><span data-stu-id="d936c-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="d936c-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="d936c-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="d936c-108">curriedOp: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="d936c-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d936c-109">Funkce, která vrací operace.</span><span class="sxs-lookup"><span data-stu-id="d936c-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj"></a><span data-ttu-id="d936c-110">Výstup: (t, ' U) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="d936c-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d936c-111">Nová operace `op` , která `op(t, u)` je ekvivalentem `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="d936c-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d936c-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d936c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d936c-113">'S</span><span class="sxs-lookup"><span data-stu-id="d936c-113">'T</span></span>

<span data-ttu-id="d936c-114">Typ prvního argumentu funkce curryfikované</span><span class="sxs-lookup"><span data-stu-id="d936c-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="d936c-115">U</span><span class="sxs-lookup"><span data-stu-id="d936c-115">'U</span></span>

<span data-ttu-id="d936c-116">Typ druhého argumentu funkce curryfikované</span><span class="sxs-lookup"><span data-stu-id="d936c-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="d936c-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="d936c-117">See Also</span></span>

- [<span data-ttu-id="d936c-118">Microsoft. proUncurriedOp. Canon.</span><span class="sxs-lookup"><span data-stu-id="d936c-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)