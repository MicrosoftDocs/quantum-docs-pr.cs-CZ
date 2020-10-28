---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: 359c0b2a9dd56445fb39fadc6580809dd9fbf628
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698800"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="14aa9-102">UncurriedOp – funkce</span><span class="sxs-lookup"><span data-stu-id="14aa9-102">UncurriedOp function</span></span>

<span data-ttu-id="14aa9-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="14aa9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="14aa9-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="14aa9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="14aa9-105">Funkce, která vrací operace, vrací novou operaci, která přijímá oba vstupy jako řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="14aa9-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="14aa9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="14aa9-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="14aa9-107">curriedOp: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14aa9-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="14aa9-108">Funkce, která vrací operace.</span><span class="sxs-lookup"><span data-stu-id="14aa9-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="14aa9-109">Výstup: (t, ' U) => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14aa9-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="14aa9-110">Nová operace `op` , která `op(t, u)` je ekvivalentem `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="14aa9-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="14aa9-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="14aa9-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="14aa9-112">'S</span><span class="sxs-lookup"><span data-stu-id="14aa9-112">'T</span></span>

<span data-ttu-id="14aa9-113">Typ prvního vstupu k operaci curryfikované</span><span class="sxs-lookup"><span data-stu-id="14aa9-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="14aa9-114">U</span><span class="sxs-lookup"><span data-stu-id="14aa9-114">'U</span></span>

<span data-ttu-id="14aa9-115">Typ druhého vstupu na operaci curryfikované.</span><span class="sxs-lookup"><span data-stu-id="14aa9-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="14aa9-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="14aa9-116">See Also</span></span>

- [<span data-ttu-id="14aa9-117">Microsoft. proUncurriedOpC. Canon.</span><span class="sxs-lookup"><span data-stu-id="14aa9-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="14aa9-118">Microsoft. proUncurriedOpA. Canon.</span><span class="sxs-lookup"><span data-stu-id="14aa9-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="14aa9-119">Microsoft. proUncurriedOpCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="14aa9-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)