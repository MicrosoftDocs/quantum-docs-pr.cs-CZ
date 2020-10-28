---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: Operace ApplyToHeadA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: ba060243cb01782fd8529e0b05ee7258a66314f5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704792"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="7c53d-102">Operace ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="7c53d-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="7c53d-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7c53d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7c53d-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7c53d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7c53d-105">Použije operaci na první prvek pole.</span><span class="sxs-lookup"><span data-stu-id="7c53d-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="7c53d-106">Popis</span><span class="sxs-lookup"><span data-stu-id="7c53d-106">Description</span></span>

<span data-ttu-id="7c53d-107">Daná operace `op` a pole cílů `targets` platí `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="7c53d-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="7c53d-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="7c53d-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="7c53d-109">op: t => ADJ. [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c53d-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7c53d-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="7c53d-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="7c53d-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="7c53d-111">targets : 'T[]</span></span>

<span data-ttu-id="7c53d-112">Pole cílů, na které se první použije `op` .</span><span class="sxs-lookup"><span data-stu-id="7c53d-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c53d-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c53d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7c53d-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7c53d-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7c53d-115">'S</span><span class="sxs-lookup"><span data-stu-id="7c53d-115">'T</span></span>

<span data-ttu-id="7c53d-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="7c53d-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c53d-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="7c53d-117">See Also</span></span>

- [<span data-ttu-id="7c53d-118">Microsoft. proApplyToHead. Canon.</span><span class="sxs-lookup"><span data-stu-id="7c53d-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="7c53d-119">Microsoft. proApplyToHeadC. Canon.</span><span class="sxs-lookup"><span data-stu-id="7c53d-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="7c53d-120">Microsoft. proApplyToHeadCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="7c53d-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)