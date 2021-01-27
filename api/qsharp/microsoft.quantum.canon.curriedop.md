---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: f811347d65a6460690163e9df631979c906bd89f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840769"
---
# <a name="curriedop-function"></a><span data-ttu-id="3c306-102">CurriedOp – funkce</span><span class="sxs-lookup"><span data-stu-id="3c306-102">CurriedOp function</span></span>

<span data-ttu-id="3c306-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3c306-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3c306-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c306-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c306-105">Vrátí curryfikované verzi operace se dvěma vstupy.</span><span class="sxs-lookup"><span data-stu-id="3c306-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="3c306-106">To znamená, že vzhledem k operaci se dvěma vstupy Tato funkce použije Curry isomorphism $f (x, y) \equiv f (x) (y) $ a vrátí operaci jednoho vstupu, který vrátí operaci jednoho vstupu.</span><span class="sxs-lookup"><span data-stu-id="3c306-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="3c306-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="3c306-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="3c306-108">op: (t, ' U) => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c306-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3c306-109">Operace, jejíž vstup je pár.</span><span class="sxs-lookup"><span data-stu-id="3c306-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="3c306-110">Výstup: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c306-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3c306-111">Operace, která přijímá první prvek páru a vrátí operaci, která přijímá jako svůj vstup druhý prvek vstupu původní operace.</span><span class="sxs-lookup"><span data-stu-id="3c306-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3c306-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="3c306-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3c306-113">'S</span><span class="sxs-lookup"><span data-stu-id="3c306-113">'T</span></span>

<span data-ttu-id="3c306-114">Typ první součásti funkce definované na dvojicích.</span><span class="sxs-lookup"><span data-stu-id="3c306-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="3c306-115">U</span><span class="sxs-lookup"><span data-stu-id="3c306-115">'U</span></span>

<span data-ttu-id="3c306-116">Typ druhé komponenty funkce definované na dvojicích.</span><span class="sxs-lookup"><span data-stu-id="3c306-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c306-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="3c306-117">Remarks</span></span>

<span data-ttu-id="3c306-118">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="3c306-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```