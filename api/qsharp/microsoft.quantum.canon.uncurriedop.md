---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: cad508f166d4af805cb98cd21a0260d9babb6a4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204636"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="03690-102">UncurriedOp – funkce</span><span class="sxs-lookup"><span data-stu-id="03690-102">UncurriedOp function</span></span>

<span data-ttu-id="03690-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="03690-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="03690-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03690-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03690-105">Funkce, která vrací operace, vrací novou operaci, která přijímá oba vstupy jako řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="03690-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="03690-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="03690-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="03690-107">curriedOp: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="03690-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="03690-108">Funkce, která vrací operace.</span><span class="sxs-lookup"><span data-stu-id="03690-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="03690-109">Výstup: (t, ' U) => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="03690-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="03690-110">Nová operace `op` , která `op(t, u)` je ekvivalentem `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="03690-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="03690-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="03690-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="03690-112">'S</span><span class="sxs-lookup"><span data-stu-id="03690-112">'T</span></span>

<span data-ttu-id="03690-113">Typ prvního vstupu k operaci curryfikované</span><span class="sxs-lookup"><span data-stu-id="03690-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="03690-114">U</span><span class="sxs-lookup"><span data-stu-id="03690-114">'U</span></span>

<span data-ttu-id="03690-115">Typ druhého vstupu na operaci curryfikované.</span><span class="sxs-lookup"><span data-stu-id="03690-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="03690-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="03690-116">See Also</span></span>

- [<span data-ttu-id="03690-117">Microsoft. proUncurriedOpC. Canon.</span><span class="sxs-lookup"><span data-stu-id="03690-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="03690-118">Microsoft. proUncurriedOpA. Canon.</span><span class="sxs-lookup"><span data-stu-id="03690-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="03690-119">Microsoft. proUncurriedOpCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="03690-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)