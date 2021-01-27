---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: Operace ApplyIfOneA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 1593f565e950a9410df0ae9de59e6d0e6a7b99b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844933"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="7e68c-102">Operace ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="7e68c-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="7e68c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7e68c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7e68c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7e68c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7e68c-105">Aplikuje na jednu operaci sousedících hodnot s hodnotou klasického výsledku.</span><span class="sxs-lookup"><span data-stu-id="7e68c-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="7e68c-106">Popis</span><span class="sxs-lookup"><span data-stu-id="7e68c-106">Description</span></span>

<span data-ttu-id="7e68c-107">`op`Pokud je zadaná operace a výsledná hodnota `result` , platí `op` pro pravidlo `target` if `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="7e68c-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="7e68c-108">`Zero`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="7e68c-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="7e68c-109">Přípona `A` označuje, že operace, která se má použít, je sousední.</span><span class="sxs-lookup"><span data-stu-id="7e68c-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="7e68c-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="7e68c-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="7e68c-111">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="7e68c-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="7e68c-112">Výsledek měření, který určuje, zda je použita možnost op nebo ne.</span><span class="sxs-lookup"><span data-stu-id="7e68c-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="7e68c-113">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="7e68c-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="7e68c-114">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="7e68c-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="7e68c-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="7e68c-115">target : 'T</span></span>

<span data-ttu-id="7e68c-116">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="7e68c-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7e68c-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e68c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7e68c-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7e68c-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7e68c-119">'S</span><span class="sxs-lookup"><span data-stu-id="7e68c-119">'T</span></span>

<span data-ttu-id="7e68c-120">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="7e68c-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e68c-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="7e68c-121">See Also</span></span>

- [<span data-ttu-id="7e68c-122">Microsoft. proApplyIfOneC. Canon.</span><span class="sxs-lookup"><span data-stu-id="7e68c-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="7e68c-123">Microsoft. proApplyIfOneA. Canon.</span><span class="sxs-lookup"><span data-stu-id="7e68c-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="7e68c-124">Microsoft. proApplyIfOneCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="7e68c-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)