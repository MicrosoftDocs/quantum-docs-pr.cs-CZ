---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: Operace ApplyIfOneCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 29801ed0bec08d0ab818f237feb17c2a2a7af1e4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218576"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="6a3ec-102">Operace ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="6a3ec-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="6a3ec-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6a3ec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6a3ec-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6a3ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6a3ec-105">Aplikuje jednotnou operaci v rámci klasické hodnoty výsledků.</span><span class="sxs-lookup"><span data-stu-id="6a3ec-105">Applies a unitary operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6a3ec-106">Popis</span><span class="sxs-lookup"><span data-stu-id="6a3ec-106">Description</span></span>

<span data-ttu-id="6a3ec-107">`op`Pokud je zadaná operace a výsledná hodnota `result` , platí `op` pro pravidlo `target` if `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="6a3ec-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="6a3ec-108">`Zero`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="6a3ec-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="6a3ec-109">Přípona `CA` označuje, že operace, která se má použít, je jednotná (přivedená a přiléhající).</span><span class="sxs-lookup"><span data-stu-id="6a3ec-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="6a3ec-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="6a3ec-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="6a3ec-111">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="6a3ec-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="6a3ec-112">Výsledek měření, který určuje, zda je použita možnost op nebo ne.</span><span class="sxs-lookup"><span data-stu-id="6a3ec-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="6a3ec-113">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="6a3ec-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6a3ec-114">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="6a3ec-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="6a3ec-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="6a3ec-115">target : 'T</span></span>

<span data-ttu-id="6a3ec-116">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="6a3ec-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6a3ec-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a3ec-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6a3ec-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6a3ec-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6a3ec-119">'S</span><span class="sxs-lookup"><span data-stu-id="6a3ec-119">'T</span></span>

<span data-ttu-id="6a3ec-120">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="6a3ec-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a3ec-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="6a3ec-121">See Also</span></span>

- [<span data-ttu-id="6a3ec-122">Microsoft. proApplyIfOneC. Canon.</span><span class="sxs-lookup"><span data-stu-id="6a3ec-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="6a3ec-123">Microsoft. proApplyIfOneA. Canon.</span><span class="sxs-lookup"><span data-stu-id="6a3ec-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="6a3ec-124">Microsoft. proApplyIfOneCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="6a3ec-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)