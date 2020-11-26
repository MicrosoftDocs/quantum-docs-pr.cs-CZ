---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: Operace ApplyToHeadC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 2b7321a6c385e2d98a0e91a8f58091ea8dc43ff4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208597"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="61e5b-102">Operace ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="61e5b-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="61e5b-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="61e5b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="61e5b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="61e5b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="61e5b-105">Použije operaci na první prvek pole.</span><span class="sxs-lookup"><span data-stu-id="61e5b-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="61e5b-106">Popis</span><span class="sxs-lookup"><span data-stu-id="61e5b-106">Description</span></span>

<span data-ttu-id="61e5b-107">Daná operace `op` a pole cílů `targets` platí `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="61e5b-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="61e5b-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="61e5b-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="61e5b-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="61e5b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="61e5b-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="61e5b-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="61e5b-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="61e5b-111">targets : 'T[]</span></span>

<span data-ttu-id="61e5b-112">Pole cílů, na které se první použije `op` .</span><span class="sxs-lookup"><span data-stu-id="61e5b-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="61e5b-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61e5b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="61e5b-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="61e5b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="61e5b-115">'S</span><span class="sxs-lookup"><span data-stu-id="61e5b-115">'T</span></span>

<span data-ttu-id="61e5b-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="61e5b-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="61e5b-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="61e5b-117">See Also</span></span>

- [<span data-ttu-id="61e5b-118">Microsoft. proApplyToHead. Canon.</span><span class="sxs-lookup"><span data-stu-id="61e5b-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="61e5b-119">Microsoft. proApplyToHeadA. Canon.</span><span class="sxs-lookup"><span data-stu-id="61e5b-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="61e5b-120">Microsoft. proApplyToHeadCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="61e5b-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)