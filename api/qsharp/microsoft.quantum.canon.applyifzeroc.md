---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: Operace ApplyIfZeroC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: cfc2a659f4da011baadff1a0d6a20a2a36d0a285
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705224"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="7696f-102">Operace ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="7696f-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="7696f-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7696f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7696f-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7696f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7696f-105">Aplikuje přizpůsobitelné operace s podmínkou pro klasický výsledek s hodnotou nula.</span><span class="sxs-lookup"><span data-stu-id="7696f-105">Applies a controllable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="7696f-106">Popis</span><span class="sxs-lookup"><span data-stu-id="7696f-106">Description</span></span>

<span data-ttu-id="7696f-107">`op`Pokud je zadaná operace a výsledná hodnota `result` , platí `op` pro pravidlo `target` if `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="7696f-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="7696f-108">`One`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="7696f-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="7696f-109">Přípona `C` označuje, že operace, která se má použít, je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="7696f-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="7696f-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="7696f-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="7696f-111">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="7696f-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="7696f-112">Výsledek měření, který určuje, zda je použita možnost op nebo ne.</span><span class="sxs-lookup"><span data-stu-id="7696f-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="7696f-113">op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="7696f-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="7696f-114">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="7696f-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="7696f-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="7696f-115">target : 'T</span></span>

<span data-ttu-id="7696f-116">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="7696f-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7696f-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7696f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7696f-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7696f-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7696f-119">'S</span><span class="sxs-lookup"><span data-stu-id="7696f-119">'T</span></span>

<span data-ttu-id="7696f-120">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="7696f-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7696f-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="7696f-121">See Also</span></span>

- [<span data-ttu-id="7696f-122">Microsoft. proApplyIfZeroC. Canon.</span><span class="sxs-lookup"><span data-stu-id="7696f-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="7696f-123">Microsoft. proApplyIfZeroA. Canon.</span><span class="sxs-lookup"><span data-stu-id="7696f-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="7696f-124">Microsoft. proApplyIfZeroCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="7696f-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)