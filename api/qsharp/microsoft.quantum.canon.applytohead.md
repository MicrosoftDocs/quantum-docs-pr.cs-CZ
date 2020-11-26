---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: Operace ApplyToHead
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 35f19cbb1090e974e18f338239764c9c8b854116
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217335"
---
# <a name="applytohead-operation"></a><span data-ttu-id="4e7ef-102">Operace ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="4e7ef-102">ApplyToHead operation</span></span>

<span data-ttu-id="4e7ef-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4e7ef-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4e7ef-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4e7ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4e7ef-105">Použije operaci na první prvek pole.</span><span class="sxs-lookup"><span data-stu-id="4e7ef-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="4e7ef-106">Popis</span><span class="sxs-lookup"><span data-stu-id="4e7ef-106">Description</span></span>

<span data-ttu-id="4e7ef-107">Daná operace `op` a pole cílů `targets` platí `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="4e7ef-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="4e7ef-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="4e7ef-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="4e7ef-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e7ef-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4e7ef-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="4e7ef-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4e7ef-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="4e7ef-111">targets : 'T[]</span></span>

<span data-ttu-id="4e7ef-112">Pole cílů, na které se první použije `op` .</span><span class="sxs-lookup"><span data-stu-id="4e7ef-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4e7ef-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e7ef-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4e7ef-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4e7ef-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4e7ef-115">'S</span><span class="sxs-lookup"><span data-stu-id="4e7ef-115">'T</span></span>

<span data-ttu-id="4e7ef-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="4e7ef-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e7ef-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="4e7ef-117">See Also</span></span>

- [<span data-ttu-id="4e7ef-118">Microsoft. proApplyToHeadA. Canon.</span><span class="sxs-lookup"><span data-stu-id="4e7ef-118">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="4e7ef-119">Microsoft. proApplyToHeadC. Canon.</span><span class="sxs-lookup"><span data-stu-id="4e7ef-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="4e7ef-120">Microsoft. proApplyToHeadCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="4e7ef-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)