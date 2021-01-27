---
uid: Microsoft.Quantum.Canon.Delay
title: Operace zpoždění
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: c8ba128e44a9b217ec196e39ff1df639ef276784
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840645"
---
# <a name="delay-operation"></a><span data-ttu-id="0f8e9-102">Operace zpoždění</span><span class="sxs-lookup"><span data-stu-id="0f8e9-102">Delay operation</span></span>

<span data-ttu-id="0f8e9-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0f8e9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0f8e9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f8e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0f8e9-105">Aplikuje danou operaci na zpoždění.</span><span class="sxs-lookup"><span data-stu-id="0f8e9-105">Applies a given operation with a delay.</span></span>

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a><span data-ttu-id="0f8e9-106">Popis</span><span class="sxs-lookup"><span data-stu-id="0f8e9-106">Description</span></span>

<span data-ttu-id="0f8e9-107">Po předané operaci a vstupu k této operaci se operace aplikuje, jakmile bude poskytnut další vstup.</span><span class="sxs-lookup"><span data-stu-id="0f8e9-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="0f8e9-108">Konkrétně výraz `Delay(op, arg, _)` je operace, která se vztahuje `op` na `arg` při volání metody.</span><span class="sxs-lookup"><span data-stu-id="0f8e9-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="0f8e9-109">Výraz `Delay(op,arg,_)` umožňuje zpožděnou aplikaci `op` .</span><span class="sxs-lookup"><span data-stu-id="0f8e9-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="0f8e9-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="0f8e9-110">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="0f8e9-111">op: t => ' U</span><span class="sxs-lookup"><span data-stu-id="0f8e9-111">op : 'T => 'U</span></span> 

<span data-ttu-id="0f8e9-112">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="0f8e9-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="0f8e9-113">ARG: t</span><span class="sxs-lookup"><span data-stu-id="0f8e9-113">arg : 'T</span></span>

<span data-ttu-id="0f8e9-114">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="0f8e9-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="0f8e9-115">AUX: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f8e9-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="0f8e9-116">Argument použitý ke zpoždění použití operace pomocí částečné aplikace</span><span class="sxs-lookup"><span data-stu-id="0f8e9-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--u"></a><span data-ttu-id="0f8e9-117">Výstup: ' U</span><span class="sxs-lookup"><span data-stu-id="0f8e9-117">Output : 'U</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0f8e9-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="0f8e9-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0f8e9-119">'S</span><span class="sxs-lookup"><span data-stu-id="0f8e9-119">'T</span></span>

<span data-ttu-id="0f8e9-120">Vstupní typ operace, která se má zpozdit</span><span class="sxs-lookup"><span data-stu-id="0f8e9-120">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="0f8e9-121">U</span><span class="sxs-lookup"><span data-stu-id="0f8e9-121">'U</span></span>

<span data-ttu-id="0f8e9-122">Návratový typ operace, která se má zpozdit.</span><span class="sxs-lookup"><span data-stu-id="0f8e9-122">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f8e9-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="0f8e9-123">See Also</span></span>

- [<span data-ttu-id="0f8e9-124">Microsoft. proDelayC. Canon.</span><span class="sxs-lookup"><span data-stu-id="0f8e9-124">Microsoft.Quantum.Canon.DelayC</span></span>](xref:Microsoft.Quantum.Canon.DelayC)
- [<span data-ttu-id="0f8e9-125">Microsoft. nečinnosti. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="0f8e9-125">Microsoft.Quantum.Canon.DelayA</span></span>](xref:Microsoft.Quantum.Canon.DelayA)
- [<span data-ttu-id="0f8e9-126">Microsoft. proDelayCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="0f8e9-126">Microsoft.Quantum.Canon.DelayCA</span></span>](xref:Microsoft.Quantum.Canon.DelayCA)
- [<span data-ttu-id="0f8e9-127">Microsoft. prodoby. Canon. zpoždění</span><span class="sxs-lookup"><span data-stu-id="0f8e9-127">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)