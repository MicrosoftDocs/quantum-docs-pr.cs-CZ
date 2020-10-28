---
uid: Microsoft.Quantum.Canon.DelayA
title: Operace zpoždění
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 77c40633824ccd9250252804b08d7400936515dd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704241"
---
# <a name="delaya-operation"></a><span data-ttu-id="a2028-102">Operace zpoždění</span><span class="sxs-lookup"><span data-stu-id="a2028-102">DelayA operation</span></span>

<span data-ttu-id="a2028-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a2028-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a2028-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a2028-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a2028-105">Aplikuje danou operaci na zpoždění.</span><span class="sxs-lookup"><span data-stu-id="a2028-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a><span data-ttu-id="a2028-106">Popis</span><span class="sxs-lookup"><span data-stu-id="a2028-106">Description</span></span>

<span data-ttu-id="a2028-107">Po předané operaci a vstupu k této operaci se operace aplikuje, jakmile bude poskytnut další vstup.</span><span class="sxs-lookup"><span data-stu-id="a2028-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="a2028-108">Konkrétně výraz `Delay(op, arg, _)` je operace, která se vztahuje `op` na `arg` při volání metody.</span><span class="sxs-lookup"><span data-stu-id="a2028-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="a2028-109">Výraz `Delay(op,arg,_)` umožňuje zpožděnou aplikaci `op` .</span><span class="sxs-lookup"><span data-stu-id="a2028-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="a2028-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="a2028-110">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="a2028-111">op: t => ADJ. [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2028-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a2028-112">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="a2028-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="a2028-113">ARG: t</span><span class="sxs-lookup"><span data-stu-id="a2028-113">arg : 'T</span></span>

<span data-ttu-id="a2028-114">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="a2028-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="a2028-115">AUX: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2028-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="a2028-116">Argument použitý ke zpoždění použití operace pomocí částečné aplikace</span><span class="sxs-lookup"><span data-stu-id="a2028-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a2028-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2028-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a2028-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a2028-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a2028-119">'S</span><span class="sxs-lookup"><span data-stu-id="a2028-119">'T</span></span>

<span data-ttu-id="a2028-120">Vstupní typ operace, která se má zpozdit</span><span class="sxs-lookup"><span data-stu-id="a2028-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2028-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="a2028-121">See Also</span></span>

- [<span data-ttu-id="a2028-122">Microsoft... Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="a2028-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="a2028-123">Microsoft. prodoby. Canon. zpoždění</span><span class="sxs-lookup"><span data-stu-id="a2028-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)