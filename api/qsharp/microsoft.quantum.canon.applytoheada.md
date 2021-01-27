---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: Operace ApplyToHeadA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 290347ff54492c4291db540e82cedcdd822a354e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850642"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="e6819-102">Operace ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="e6819-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="e6819-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e6819-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e6819-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6819-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6819-105">Použije operaci na první prvek pole.</span><span class="sxs-lookup"><span data-stu-id="e6819-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="e6819-106">Popis</span><span class="sxs-lookup"><span data-stu-id="e6819-106">Description</span></span>

<span data-ttu-id="e6819-107">Daná operace `op` a pole cílů `targets` platí `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="e6819-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="e6819-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="e6819-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="e6819-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="e6819-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e6819-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="e6819-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e6819-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="e6819-111">targets : 'T[]</span></span>

<span data-ttu-id="e6819-112">Pole cílů, na které se první použije `op` .</span><span class="sxs-lookup"><span data-stu-id="e6819-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e6819-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6819-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e6819-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e6819-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e6819-115">'S</span><span class="sxs-lookup"><span data-stu-id="e6819-115">'T</span></span>

<span data-ttu-id="e6819-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="e6819-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6819-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="e6819-117">See Also</span></span>

- [<span data-ttu-id="e6819-118">Microsoft. proApplyToHead. Canon.</span><span class="sxs-lookup"><span data-stu-id="e6819-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="e6819-119">Microsoft. proApplyToHeadC. Canon.</span><span class="sxs-lookup"><span data-stu-id="e6819-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="e6819-120">Microsoft. proApplyToHeadCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="e6819-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)