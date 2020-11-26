---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: Operace ApplyToHeadCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: f28cff599e06090145fac860dbaf8274c966f80a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208546"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="ea7cf-102">Operace ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="ea7cf-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="ea7cf-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ea7cf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ea7cf-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ea7cf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ea7cf-105">Použije operaci na první prvek pole.</span><span class="sxs-lookup"><span data-stu-id="ea7cf-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ea7cf-106">Popis</span><span class="sxs-lookup"><span data-stu-id="ea7cf-106">Description</span></span>

<span data-ttu-id="ea7cf-107">Daná operace `op` a pole cílů `targets` platí `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="ea7cf-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="ea7cf-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="ea7cf-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="ea7cf-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="ea7cf-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ea7cf-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="ea7cf-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ea7cf-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="ea7cf-111">targets : 'T[]</span></span>

<span data-ttu-id="ea7cf-112">Pole cílů, na které se první použije `op` .</span><span class="sxs-lookup"><span data-stu-id="ea7cf-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea7cf-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea7cf-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ea7cf-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ea7cf-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ea7cf-115">'S</span><span class="sxs-lookup"><span data-stu-id="ea7cf-115">'T</span></span>

<span data-ttu-id="ea7cf-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="ea7cf-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea7cf-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="ea7cf-117">See Also</span></span>

- [<span data-ttu-id="ea7cf-118">Microsoft. proApplyToHead. Canon.</span><span class="sxs-lookup"><span data-stu-id="ea7cf-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="ea7cf-119">Microsoft. proApplyToHeadA. Canon.</span><span class="sxs-lookup"><span data-stu-id="ea7cf-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="ea7cf-120">Microsoft. proApplyToHeadC. Canon.</span><span class="sxs-lookup"><span data-stu-id="ea7cf-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)