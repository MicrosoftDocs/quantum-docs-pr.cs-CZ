---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: Operace ApplyToElementA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: f34089c2a45de281507cb79bde8a8cb9d2fefe47
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704921"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="6fd9c-102">Operace ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="6fd9c-102">ApplyToElementA operation</span></span>

<span data-ttu-id="6fd9c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6fd9c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6fd9c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6fd9c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6fd9c-105">Použije operaci na daný prvek pole.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="6fd9c-106">Popis</span><span class="sxs-lookup"><span data-stu-id="6fd9c-106">Description</span></span>

<span data-ttu-id="6fd9c-107">Pro danou operaci se `op` použije index `index` a pole cílů `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="6fd9c-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="6fd9c-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="6fd9c-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="6fd9c-109">op: t => ADJ. [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6fd9c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="6fd9c-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="6fd9c-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6fd9c-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6fd9c-112">Index do pole cílů.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="6fd9c-113">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="6fd9c-113">targets : 'T[]</span></span>

<span data-ttu-id="6fd9c-114">Pole možných cílů pro `op` .</span><span class="sxs-lookup"><span data-stu-id="6fd9c-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6fd9c-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6fd9c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6fd9c-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6fd9c-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6fd9c-117">'S</span><span class="sxs-lookup"><span data-stu-id="6fd9c-117">'T</span></span>

<span data-ttu-id="6fd9c-118">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6fd9c-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="6fd9c-119">See Also</span></span>

- [<span data-ttu-id="6fd9c-120">Microsoft. proApplyToElement. Canon.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="6fd9c-121">Microsoft. proApplyToElementC. Canon.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="6fd9c-122">Microsoft. proApplyToElementCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)