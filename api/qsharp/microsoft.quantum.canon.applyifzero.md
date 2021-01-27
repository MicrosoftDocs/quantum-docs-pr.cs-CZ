---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: Operace ApplyIfZero
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 215b71a8d2e4f8a22df05b210824bc40a969b6f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841745"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="fb26a-102">Operace ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="fb26a-102">ApplyIfZero operation</span></span>

<span data-ttu-id="fb26a-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fb26a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fb26a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fb26a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fb26a-105">Aplikuje operaci s podmíněnou hodnotou pro klasický výsledek nula.</span><span class="sxs-lookup"><span data-stu-id="fb26a-105">Applies an operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="fb26a-106">Popis</span><span class="sxs-lookup"><span data-stu-id="fb26a-106">Description</span></span>

<span data-ttu-id="fb26a-107">`op`Pokud je zadaná operace a výsledná hodnota `result` , platí `op` pro pravidlo `target` if `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="fb26a-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="fb26a-108">`One`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="fb26a-108">If `One`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="fb26a-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="fb26a-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="fb26a-110">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="fb26a-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="fb26a-111">Výsledek měření, který určuje, zda je použita možnost op nebo ne.</span><span class="sxs-lookup"><span data-stu-id="fb26a-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="fb26a-112">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fb26a-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fb26a-113">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="fb26a-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="fb26a-114">cíl: t</span><span class="sxs-lookup"><span data-stu-id="fb26a-114">target : 'T</span></span>

<span data-ttu-id="fb26a-115">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="fb26a-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fb26a-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fb26a-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fb26a-117">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="fb26a-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fb26a-118">'S</span><span class="sxs-lookup"><span data-stu-id="fb26a-118">'T</span></span>

<span data-ttu-id="fb26a-119">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="fb26a-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb26a-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="fb26a-120">See Also</span></span>

- [<span data-ttu-id="fb26a-121">Microsoft. proApplyIfZeroC. Canon.</span><span class="sxs-lookup"><span data-stu-id="fb26a-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="fb26a-122">Microsoft. proApplyIfZeroA. Canon.</span><span class="sxs-lookup"><span data-stu-id="fb26a-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="fb26a-123">Microsoft. proApplyIfZeroCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="fb26a-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)