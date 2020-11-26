---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: Operace ApplyToElementA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: e8318a7873476ee49d8e1e235e6c917a38ee6200
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208869"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="1b064-102">Operace ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="1b064-102">ApplyToElementA operation</span></span>

<span data-ttu-id="1b064-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1b064-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1b064-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b064-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1b064-105">Použije operaci na daný prvek pole.</span><span class="sxs-lookup"><span data-stu-id="1b064-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="1b064-106">Popis</span><span class="sxs-lookup"><span data-stu-id="1b064-106">Description</span></span>

<span data-ttu-id="1b064-107">Pro danou operaci se `op` použije index `index` a pole cílů `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="1b064-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="1b064-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="1b064-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="1b064-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="1b064-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="1b064-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="1b064-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="1b064-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1b064-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1b064-112">Index do pole cílů.</span><span class="sxs-lookup"><span data-stu-id="1b064-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="1b064-113">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="1b064-113">targets : 'T[]</span></span>

<span data-ttu-id="1b064-114">Pole možných cílů pro `op` .</span><span class="sxs-lookup"><span data-stu-id="1b064-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1b064-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1b064-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1b064-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="1b064-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1b064-117">'S</span><span class="sxs-lookup"><span data-stu-id="1b064-117">'T</span></span>

<span data-ttu-id="1b064-118">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="1b064-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b064-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="1b064-119">See Also</span></span>

- [<span data-ttu-id="1b064-120">Microsoft. proApplyToElement. Canon.</span><span class="sxs-lookup"><span data-stu-id="1b064-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="1b064-121">Microsoft. proApplyToElementC. Canon.</span><span class="sxs-lookup"><span data-stu-id="1b064-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="1b064-122">Microsoft. proApplyToElementCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="1b064-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)