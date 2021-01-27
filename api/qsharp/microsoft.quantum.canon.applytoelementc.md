---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: Operace ApplyToElementC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bc63b6b591781a6283b872ef0c2509094a656b4c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850744"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="03714-102">Operace ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="03714-102">ApplyToElementC operation</span></span>

<span data-ttu-id="03714-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="03714-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="03714-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03714-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03714-105">Použije operaci na daný prvek pole.</span><span class="sxs-lookup"><span data-stu-id="03714-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="03714-106">Popis</span><span class="sxs-lookup"><span data-stu-id="03714-106">Description</span></span>

<span data-ttu-id="03714-107">Pro danou operaci se `op` použije index `index` a pole cílů `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="03714-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="03714-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="03714-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="03714-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="03714-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="03714-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="03714-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="03714-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="03714-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="03714-112">Index do pole cílů.</span><span class="sxs-lookup"><span data-stu-id="03714-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="03714-113">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="03714-113">targets : 'T[]</span></span>

<span data-ttu-id="03714-114">Pole možných cílů pro `op` .</span><span class="sxs-lookup"><span data-stu-id="03714-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="03714-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="03714-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="03714-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="03714-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="03714-117">'S</span><span class="sxs-lookup"><span data-stu-id="03714-117">'T</span></span>

<span data-ttu-id="03714-118">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="03714-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="03714-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="03714-119">See Also</span></span>

- [<span data-ttu-id="03714-120">Microsoft. proApplyToElement. Canon.</span><span class="sxs-lookup"><span data-stu-id="03714-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="03714-121">Microsoft. proApplyToElementA. Canon.</span><span class="sxs-lookup"><span data-stu-id="03714-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="03714-122">Microsoft. proApplyToElementCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="03714-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)