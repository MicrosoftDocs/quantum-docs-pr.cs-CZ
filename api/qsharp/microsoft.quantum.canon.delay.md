---
uid: Microsoft.Quantum.Canon.Delay
title: Operace zpoždění
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: f9f0e5c3120eb69bd7431d52d6cde5e846ffbe4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704256"
---
# <a name="delay-operation"></a><span data-ttu-id="94082-102">Operace zpoždění</span><span class="sxs-lookup"><span data-stu-id="94082-102">Delay operation</span></span>

<span data-ttu-id="94082-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="94082-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="94082-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="94082-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="94082-105">Aplikuje danou operaci na zpoždění.</span><span class="sxs-lookup"><span data-stu-id="94082-105">Applies a given operation with a delay.</span></span>

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a><span data-ttu-id="94082-106">Popis</span><span class="sxs-lookup"><span data-stu-id="94082-106">Description</span></span>

<span data-ttu-id="94082-107">Po předané operaci a vstupu k této operaci se operace aplikuje, jakmile bude poskytnut další vstup.</span><span class="sxs-lookup"><span data-stu-id="94082-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="94082-108">Konkrétně výraz `Delay(op, arg, _)` je operace, která se vztahuje `op` na `arg` při volání metody.</span><span class="sxs-lookup"><span data-stu-id="94082-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="94082-109">Výraz `Delay(op,arg,_)` umožňuje zpožděnou aplikaci `op` .</span><span class="sxs-lookup"><span data-stu-id="94082-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="94082-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="94082-110">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="94082-111">op: t => ' U</span><span class="sxs-lookup"><span data-stu-id="94082-111">op : 'T => 'U</span></span> 

<span data-ttu-id="94082-112">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="94082-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="94082-113">ARG: t</span><span class="sxs-lookup"><span data-stu-id="94082-113">arg : 'T</span></span>

<span data-ttu-id="94082-114">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="94082-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="94082-115">AUX: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94082-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="94082-116">Argument použitý ke zpoždění použití operace pomocí částečné aplikace</span><span class="sxs-lookup"><span data-stu-id="94082-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--u"></a><span data-ttu-id="94082-117">Výstup: ' U</span><span class="sxs-lookup"><span data-stu-id="94082-117">Output : 'U</span></span>



## <a name="type-parameters"></a><span data-ttu-id="94082-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="94082-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="94082-119">'S</span><span class="sxs-lookup"><span data-stu-id="94082-119">'T</span></span>

<span data-ttu-id="94082-120">Vstupní typ operace, která se má zpozdit</span><span class="sxs-lookup"><span data-stu-id="94082-120">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="94082-121">U</span><span class="sxs-lookup"><span data-stu-id="94082-121">'U</span></span>

<span data-ttu-id="94082-122">Návratový typ operace, která se má zpozdit.</span><span class="sxs-lookup"><span data-stu-id="94082-122">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="94082-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="94082-123">See Also</span></span>

- [<span data-ttu-id="94082-124">Microsoft. proDelayC. Canon.</span><span class="sxs-lookup"><span data-stu-id="94082-124">Microsoft.Quantum.Canon.DelayC</span></span>](xref:Microsoft.Quantum.Canon.DelayC)
- [<span data-ttu-id="94082-125">Microsoft. nečinnosti. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="94082-125">Microsoft.Quantum.Canon.DelayA</span></span>](xref:Microsoft.Quantum.Canon.DelayA)
- [<span data-ttu-id="94082-126">Microsoft. proDelayCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="94082-126">Microsoft.Quantum.Canon.DelayCA</span></span>](xref:Microsoft.Quantum.Canon.DelayCA)
- [<span data-ttu-id="94082-127">Microsoft. prodoby. Canon. zpoždění</span><span class="sxs-lookup"><span data-stu-id="94082-127">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)