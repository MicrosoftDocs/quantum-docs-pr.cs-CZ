---
uid: Microsoft.Quantum.Canon.ApplyIfZeroA
title: Operace ApplyIfZeroA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being zero.
ms.openlocfilehash: ab5b05791213da7c8bee5915764c342cb0bed851
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218491"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="b03ed-102">Operace ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="b03ed-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="b03ed-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b03ed-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b03ed-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b03ed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b03ed-105">Aplikuje operaci sousedících s hodnotou pro klasický výsledek s hodnotou nula.</span><span class="sxs-lookup"><span data-stu-id="b03ed-105">Applies an adjointable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="b03ed-106">Popis</span><span class="sxs-lookup"><span data-stu-id="b03ed-106">Description</span></span>

<span data-ttu-id="b03ed-107">`op`Pokud je zadaná operace a výsledná hodnota `result` , platí `op` pro pravidlo `target` if `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="b03ed-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="b03ed-108">`One`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="b03ed-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="b03ed-109">Přípona `A` označuje, že operace, která se má použít, je sousední.</span><span class="sxs-lookup"><span data-stu-id="b03ed-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="b03ed-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="b03ed-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="b03ed-111">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="b03ed-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="b03ed-112">Výsledek měření, který určuje, zda je použita možnost op nebo ne.</span><span class="sxs-lookup"><span data-stu-id="b03ed-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="b03ed-113">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="b03ed-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b03ed-114">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="b03ed-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="b03ed-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="b03ed-115">target : 'T</span></span>

<span data-ttu-id="b03ed-116">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="b03ed-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b03ed-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b03ed-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b03ed-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b03ed-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b03ed-119">'S</span><span class="sxs-lookup"><span data-stu-id="b03ed-119">'T</span></span>

<span data-ttu-id="b03ed-120">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="b03ed-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b03ed-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="b03ed-121">See Also</span></span>

- [<span data-ttu-id="b03ed-122">Microsoft. proApplyIfZeroC. Canon.</span><span class="sxs-lookup"><span data-stu-id="b03ed-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="b03ed-123">Microsoft. proApplyIfZeroA. Canon.</span><span class="sxs-lookup"><span data-stu-id="b03ed-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="b03ed-124">Microsoft. proApplyIfZeroCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="b03ed-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)