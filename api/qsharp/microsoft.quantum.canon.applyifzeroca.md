---
uid: Microsoft.Quantum.Canon.ApplyIfZeroCA
title: Operace ApplyIfZeroCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being zero.
ms.openlocfilehash: 4ed0660e2fe3623d0a8e4e4f3bd0bddb536b7b5c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844884"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="12761-102">Operace ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="12761-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="12761-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="12761-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="12761-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="12761-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="12761-105">Aplikuje jednotnou operaci s podmínkou pro klasický výsledek s hodnotou nula.</span><span class="sxs-lookup"><span data-stu-id="12761-105">Applies a unitary operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="12761-106">Popis</span><span class="sxs-lookup"><span data-stu-id="12761-106">Description</span></span>

<span data-ttu-id="12761-107">`op`Pokud je zadaná operace a výsledná hodnota `result` , platí `op` pro pravidlo `target` if `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="12761-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="12761-108">`One`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="12761-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="12761-109">Přípona `CA` označuje, že operace, která se má použít, je jednotná (přivedená a přiléhající).</span><span class="sxs-lookup"><span data-stu-id="12761-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="12761-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="12761-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="12761-111">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="12761-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="12761-112">Výsledek měření, který určuje, zda je použita možnost op nebo ne.</span><span class="sxs-lookup"><span data-stu-id="12761-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="12761-113">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="12761-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="12761-114">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="12761-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="12761-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="12761-115">target : 'T</span></span>

<span data-ttu-id="12761-116">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="12761-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="12761-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="12761-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="12761-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="12761-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="12761-119">'S</span><span class="sxs-lookup"><span data-stu-id="12761-119">'T</span></span>

<span data-ttu-id="12761-120">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="12761-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="12761-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="12761-121">See Also</span></span>

- [<span data-ttu-id="12761-122">Microsoft. proApplyIfZeroC. Canon.</span><span class="sxs-lookup"><span data-stu-id="12761-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="12761-123">Microsoft. proApplyIfZeroA. Canon.</span><span class="sxs-lookup"><span data-stu-id="12761-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="12761-124">Microsoft. proApplyIfZeroCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="12761-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)