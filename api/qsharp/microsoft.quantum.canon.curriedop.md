---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 6c1917d6f1ee69cb29fed1ab173106af1e206533
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216621"
---
# <a name="curriedop-function"></a><span data-ttu-id="718c5-102">CurriedOp – funkce</span><span class="sxs-lookup"><span data-stu-id="718c5-102">CurriedOp function</span></span>

<span data-ttu-id="718c5-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="718c5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="718c5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="718c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="718c5-105">Vrátí curryfikované verzi operace se dvěma vstupy.</span><span class="sxs-lookup"><span data-stu-id="718c5-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="718c5-106">To znamená, že vzhledem k operaci se dvěma vstupy Tato funkce použije Curry isomorphism $f (x, y) \equiv f (x) (y) $ a vrátí operaci jednoho vstupu, který vrátí operaci jednoho vstupu.</span><span class="sxs-lookup"><span data-stu-id="718c5-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="718c5-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="718c5-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="718c5-108">op: (t, ' U) => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="718c5-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="718c5-109">Operace, jejíž vstup je pár.</span><span class="sxs-lookup"><span data-stu-id="718c5-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="718c5-110">Výstup: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="718c5-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="718c5-111">Operace, která přijímá první prvek páru a vrátí operaci, která přijímá jako svůj vstup druhý prvek vstupu původní operace.</span><span class="sxs-lookup"><span data-stu-id="718c5-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="718c5-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="718c5-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="718c5-113">'S</span><span class="sxs-lookup"><span data-stu-id="718c5-113">'T</span></span>

<span data-ttu-id="718c5-114">Typ první součásti funkce definované na dvojicích.</span><span class="sxs-lookup"><span data-stu-id="718c5-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="718c5-115">U</span><span class="sxs-lookup"><span data-stu-id="718c5-115">'U</span></span>

<span data-ttu-id="718c5-116">Typ druhé komponenty funkce definované na dvojicích.</span><span class="sxs-lookup"><span data-stu-id="718c5-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="718c5-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="718c5-117">Remarks</span></span>

<span data-ttu-id="718c5-118">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="718c5-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```