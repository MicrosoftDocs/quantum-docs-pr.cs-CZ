---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: Operace ApplyToElementC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: c8d7841e3846ab435671f7959c724f987d8ad5a0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217573"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="9320f-102">Operace ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="9320f-102">ApplyToElementC operation</span></span>

<span data-ttu-id="9320f-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9320f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9320f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9320f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9320f-105">Použije operaci na daný prvek pole.</span><span class="sxs-lookup"><span data-stu-id="9320f-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="9320f-106">Popis</span><span class="sxs-lookup"><span data-stu-id="9320f-106">Description</span></span>

<span data-ttu-id="9320f-107">Pro danou operaci se `op` použije index `index` a pole cílů `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="9320f-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="9320f-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="9320f-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="9320f-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="9320f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="9320f-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="9320f-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="9320f-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9320f-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9320f-112">Index do pole cílů.</span><span class="sxs-lookup"><span data-stu-id="9320f-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="9320f-113">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="9320f-113">targets : 'T[]</span></span>

<span data-ttu-id="9320f-114">Pole možných cílů pro `op` .</span><span class="sxs-lookup"><span data-stu-id="9320f-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9320f-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9320f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9320f-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="9320f-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9320f-117">'S</span><span class="sxs-lookup"><span data-stu-id="9320f-117">'T</span></span>

<span data-ttu-id="9320f-118">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="9320f-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9320f-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="9320f-119">See Also</span></span>

- [<span data-ttu-id="9320f-120">Microsoft. proApplyToElement. Canon.</span><span class="sxs-lookup"><span data-stu-id="9320f-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="9320f-121">Microsoft. proApplyToElementA. Canon.</span><span class="sxs-lookup"><span data-stu-id="9320f-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="9320f-122">Microsoft. proApplyToElementCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="9320f-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)