---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: Operace ApplyToElementCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 599a8afe1ab97b0ab0d6621cabd7707faaeddda3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704897"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="53fd4-102">Operace ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="53fd4-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="53fd4-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="53fd4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="53fd4-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53fd4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53fd4-105">Použije operaci na daný prvek pole.</span><span class="sxs-lookup"><span data-stu-id="53fd4-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="53fd4-106">Popis</span><span class="sxs-lookup"><span data-stu-id="53fd4-106">Description</span></span>

<span data-ttu-id="53fd4-107">Pro danou operaci se `op` použije index `index` a pole cílů `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="53fd4-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="53fd4-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="53fd4-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="53fd4-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="53fd4-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="53fd4-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="53fd4-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="53fd4-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="53fd4-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="53fd4-112">Index do pole cílů.</span><span class="sxs-lookup"><span data-stu-id="53fd4-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="53fd4-113">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="53fd4-113">targets : 'T[]</span></span>

<span data-ttu-id="53fd4-114">Pole možných cílů pro `op` .</span><span class="sxs-lookup"><span data-stu-id="53fd4-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="53fd4-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="53fd4-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="53fd4-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="53fd4-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="53fd4-117">'S</span><span class="sxs-lookup"><span data-stu-id="53fd4-117">'T</span></span>

<span data-ttu-id="53fd4-118">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="53fd4-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="53fd4-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="53fd4-119">See Also</span></span>

- [<span data-ttu-id="53fd4-120">Microsoft. proApplyToElement. Canon.</span><span class="sxs-lookup"><span data-stu-id="53fd4-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="53fd4-121">Microsoft. proApplyToElementC. Canon.</span><span class="sxs-lookup"><span data-stu-id="53fd4-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="53fd4-122">Microsoft. proApplyToElementA. Canon.</span><span class="sxs-lookup"><span data-stu-id="53fd4-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)