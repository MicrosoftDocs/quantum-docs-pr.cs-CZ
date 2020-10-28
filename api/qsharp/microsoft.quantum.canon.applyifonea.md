---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: Operace ApplyIfOneA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 76c15aba6042c2801ecfe8470e82099c54ba3846
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705272"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="61e32-102">Operace ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="61e32-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="61e32-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="61e32-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="61e32-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="61e32-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="61e32-105">Aplikuje na jednu operaci sousedících hodnot s hodnotou klasického výsledku.</span><span class="sxs-lookup"><span data-stu-id="61e32-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="61e32-106">Popis</span><span class="sxs-lookup"><span data-stu-id="61e32-106">Description</span></span>

<span data-ttu-id="61e32-107">`op`Pokud je zadaná operace a výsledná hodnota `result` , platí `op` pro pravidlo `target` if `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="61e32-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="61e32-108">`Zero`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="61e32-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="61e32-109">Přípona `A` označuje, že operace, která se má použít, je sousední.</span><span class="sxs-lookup"><span data-stu-id="61e32-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="61e32-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="61e32-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="61e32-111">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="61e32-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="61e32-112">Výsledek měření, který určuje, zda je použita možnost op nebo ne.</span><span class="sxs-lookup"><span data-stu-id="61e32-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="61e32-113">op: t => ADJ. [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61e32-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="61e32-114">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="61e32-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="61e32-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="61e32-115">target : 'T</span></span>

<span data-ttu-id="61e32-116">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="61e32-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="61e32-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61e32-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="61e32-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="61e32-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="61e32-119">'S</span><span class="sxs-lookup"><span data-stu-id="61e32-119">'T</span></span>

<span data-ttu-id="61e32-120">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="61e32-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="61e32-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="61e32-121">See Also</span></span>

- [<span data-ttu-id="61e32-122">Microsoft. proApplyIfOneC. Canon.</span><span class="sxs-lookup"><span data-stu-id="61e32-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="61e32-123">Microsoft. proApplyIfOneA. Canon.</span><span class="sxs-lookup"><span data-stu-id="61e32-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="61e32-124">Microsoft. proApplyIfOneCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="61e32-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)