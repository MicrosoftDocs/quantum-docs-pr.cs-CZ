---
uid: Microsoft.Quantum.Canon.ApplyIfZeroA
title: Operace ApplyIfZeroA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being zero.
ms.openlocfilehash: d324cd970e8df49ceb51b6bf5c9f3c9c3ff142f9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705248"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="e4be2-102">Operace ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="e4be2-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="e4be2-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e4be2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e4be2-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e4be2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e4be2-105">Aplikuje operaci sousedících s hodnotou pro klasický výsledek s hodnotou nula.</span><span class="sxs-lookup"><span data-stu-id="e4be2-105">Applies an adjointable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="e4be2-106">Popis</span><span class="sxs-lookup"><span data-stu-id="e4be2-106">Description</span></span>

<span data-ttu-id="e4be2-107">`op`Pokud je zadaná operace a výsledná hodnota `result` , platí `op` pro pravidlo `target` if `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="e4be2-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="e4be2-108">`One`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="e4be2-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="e4be2-109">Přípona `A` označuje, že operace, která se má použít, je sousední.</span><span class="sxs-lookup"><span data-stu-id="e4be2-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="e4be2-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="e4be2-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="e4be2-111">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="e4be2-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="e4be2-112">Výsledek měření, který určuje, zda je použita možnost op nebo ne.</span><span class="sxs-lookup"><span data-stu-id="e4be2-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="e4be2-113">op: t => ADJ. [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e4be2-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="e4be2-114">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="e4be2-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="e4be2-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="e4be2-115">target : 'T</span></span>

<span data-ttu-id="e4be2-116">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="e4be2-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e4be2-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e4be2-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e4be2-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e4be2-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e4be2-119">'S</span><span class="sxs-lookup"><span data-stu-id="e4be2-119">'T</span></span>

<span data-ttu-id="e4be2-120">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="e4be2-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4be2-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="e4be2-121">See Also</span></span>

- [<span data-ttu-id="e4be2-122">Microsoft. proApplyIfZeroC. Canon.</span><span class="sxs-lookup"><span data-stu-id="e4be2-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="e4be2-123">Microsoft. proApplyIfZeroA. Canon.</span><span class="sxs-lookup"><span data-stu-id="e4be2-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="e4be2-124">Microsoft. proApplyIfZeroCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="e4be2-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)