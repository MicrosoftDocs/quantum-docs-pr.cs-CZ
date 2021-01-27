---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: Operace ApplyIfOne
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: b86aecf3dc3d02d1a6bf0c112bdc45a55a2cf087
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841769"
---
# <a name="applyifone-operation"></a><span data-ttu-id="cd645-102">Operace ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="cd645-102">ApplyIfOne operation</span></span>

<span data-ttu-id="cd645-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cd645-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cd645-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cd645-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cd645-105">Aplikuje operaci s podmíněnou hodnotou pro klasický výsledek.</span><span class="sxs-lookup"><span data-stu-id="cd645-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="cd645-106">Popis</span><span class="sxs-lookup"><span data-stu-id="cd645-106">Description</span></span>

<span data-ttu-id="cd645-107">`op`Pokud je zadaná operace a výsledná hodnota `result` , platí `op` pro pravidlo `target` if `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="cd645-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="cd645-108">`Zero`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="cd645-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="cd645-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="cd645-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="cd645-110">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="cd645-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="cd645-111">Výsledek měření, který určuje, zda je použita možnost op nebo ne.</span><span class="sxs-lookup"><span data-stu-id="cd645-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="cd645-112">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd645-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="cd645-113">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="cd645-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="cd645-114">cíl: t</span><span class="sxs-lookup"><span data-stu-id="cd645-114">target : 'T</span></span>

<span data-ttu-id="cd645-115">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="cd645-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cd645-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd645-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cd645-117">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="cd645-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cd645-118">'S</span><span class="sxs-lookup"><span data-stu-id="cd645-118">'T</span></span>

<span data-ttu-id="cd645-119">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="cd645-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd645-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="cd645-120">See Also</span></span>

- [<span data-ttu-id="cd645-121">Microsoft. proApplyIfOneC. Canon.</span><span class="sxs-lookup"><span data-stu-id="cd645-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="cd645-122">Microsoft. proApplyIfOneA. Canon.</span><span class="sxs-lookup"><span data-stu-id="cd645-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="cd645-123">Microsoft. proApplyIfOneCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="cd645-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)