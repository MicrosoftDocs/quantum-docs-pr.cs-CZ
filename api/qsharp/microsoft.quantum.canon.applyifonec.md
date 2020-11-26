---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: Operace ApplyIfOneC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: 24a00d83c1bbe6b07adb27c58fc70bc76af0a910
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209413"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="730a1-102">Operace ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="730a1-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="730a1-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="730a1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="730a1-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="730a1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="730a1-105">Aplikuje na sebe ovladatelné operace s hodnotou klasického výsledku.</span><span class="sxs-lookup"><span data-stu-id="730a1-105">Applies a controllable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="730a1-106">Popis</span><span class="sxs-lookup"><span data-stu-id="730a1-106">Description</span></span>

<span data-ttu-id="730a1-107">`op`Pokud je zadaná operace a výsledná hodnota `result` , platí `op` pro pravidlo `target` if `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="730a1-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="730a1-108">`Zero`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="730a1-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="730a1-109">Přípona `C` označuje, že operace, která se má použít, je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="730a1-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="730a1-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="730a1-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="730a1-111">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="730a1-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="730a1-112">Výsledek měření, který určuje, zda je použita možnost op nebo ne.</span><span class="sxs-lookup"><span data-stu-id="730a1-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="730a1-113">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="730a1-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="730a1-114">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="730a1-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="730a1-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="730a1-115">target : 'T</span></span>

<span data-ttu-id="730a1-116">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="730a1-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="730a1-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="730a1-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="730a1-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="730a1-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="730a1-119">'S</span><span class="sxs-lookup"><span data-stu-id="730a1-119">'T</span></span>

<span data-ttu-id="730a1-120">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="730a1-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="730a1-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="730a1-121">See Also</span></span>

- [<span data-ttu-id="730a1-122">Microsoft. proApplyIfOneC. Canon.</span><span class="sxs-lookup"><span data-stu-id="730a1-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="730a1-123">Microsoft. proApplyIfOneA. Canon.</span><span class="sxs-lookup"><span data-stu-id="730a1-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="730a1-124">Microsoft. proApplyIfOneCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="730a1-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)