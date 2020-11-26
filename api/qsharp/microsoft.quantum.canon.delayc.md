---
uid: Microsoft.Quantum.Canon.DelayC
title: Operace DelayC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7a11c3990802ff36856a90de927b38d2ede8bd9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216485"
---
# <a name="delayc-operation"></a><span data-ttu-id="e66a3-102">Operace DelayC</span><span class="sxs-lookup"><span data-stu-id="e66a3-102">DelayC operation</span></span>

<span data-ttu-id="e66a3-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e66a3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e66a3-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e66a3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e66a3-105">Aplikuje danou operaci na zpoždění.</span><span class="sxs-lookup"><span data-stu-id="e66a3-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="e66a3-106">Popis</span><span class="sxs-lookup"><span data-stu-id="e66a3-106">Description</span></span>

<span data-ttu-id="e66a3-107">Po předané operaci a vstupu k této operaci se operace aplikuje, jakmile bude poskytnut další vstup.</span><span class="sxs-lookup"><span data-stu-id="e66a3-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="e66a3-108">Konkrétně výraz `Delay(op, arg, _)` je operace, která se vztahuje `op` na `arg` při volání metody.</span><span class="sxs-lookup"><span data-stu-id="e66a3-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="e66a3-109">Výraz `Delay(op,arg,_)` umožňuje zpožděnou aplikaci `op` .</span><span class="sxs-lookup"><span data-stu-id="e66a3-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="e66a3-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="e66a3-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="e66a3-111">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="e66a3-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="e66a3-112">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="e66a3-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="e66a3-113">ARG: t</span><span class="sxs-lookup"><span data-stu-id="e66a3-113">arg : 'T</span></span>

<span data-ttu-id="e66a3-114">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="e66a3-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="e66a3-115">AUX: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e66a3-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="e66a3-116">Argument použitý ke zpoždění použití operace pomocí částečné aplikace</span><span class="sxs-lookup"><span data-stu-id="e66a3-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e66a3-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e66a3-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e66a3-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e66a3-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e66a3-119">'S</span><span class="sxs-lookup"><span data-stu-id="e66a3-119">'T</span></span>

<span data-ttu-id="e66a3-120">Vstupní typ operace, která se má zpozdit</span><span class="sxs-lookup"><span data-stu-id="e66a3-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="e66a3-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="e66a3-121">See Also</span></span>

- [<span data-ttu-id="e66a3-122">Microsoft... Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="e66a3-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="e66a3-123">Microsoft. prodoby. Canon. zpoždění</span><span class="sxs-lookup"><span data-stu-id="e66a3-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)