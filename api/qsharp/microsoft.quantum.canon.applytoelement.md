---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: Operace ApplyToElement
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 5159eee07f7398cc6194c9907a37b78a63aaf263
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850774"
---
# <a name="applytoelement-operation"></a><span data-ttu-id="15d86-102">Operace ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="15d86-102">ApplyToElement operation</span></span>

<span data-ttu-id="15d86-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="15d86-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="15d86-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="15d86-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="15d86-105">Použije operaci na daný prvek pole.</span><span class="sxs-lookup"><span data-stu-id="15d86-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="15d86-106">Popis</span><span class="sxs-lookup"><span data-stu-id="15d86-106">Description</span></span>

<span data-ttu-id="15d86-107">Pro danou operaci se `op` použije index `index` a pole cílů `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="15d86-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="15d86-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="15d86-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="15d86-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15d86-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="15d86-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="15d86-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="15d86-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="15d86-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="15d86-112">Index do pole cílů.</span><span class="sxs-lookup"><span data-stu-id="15d86-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="15d86-113">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="15d86-113">targets : 'T[]</span></span>

<span data-ttu-id="15d86-114">Pole možných cílů pro `op` .</span><span class="sxs-lookup"><span data-stu-id="15d86-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="15d86-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15d86-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="15d86-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="15d86-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="15d86-117">'S</span><span class="sxs-lookup"><span data-stu-id="15d86-117">'T</span></span>

<span data-ttu-id="15d86-118">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="15d86-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="15d86-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="15d86-119">See Also</span></span>

- [<span data-ttu-id="15d86-120">Microsoft. proApplyToElementC. Canon.</span><span class="sxs-lookup"><span data-stu-id="15d86-120">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="15d86-121">Microsoft. proApplyToElementA. Canon.</span><span class="sxs-lookup"><span data-stu-id="15d86-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="15d86-122">Microsoft. proApplyToElementCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="15d86-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)