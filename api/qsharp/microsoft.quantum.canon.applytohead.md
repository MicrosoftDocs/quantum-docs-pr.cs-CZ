---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: Operace ApplyToHead
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e5fc439f48a5c7e527b7805c35cce18eca3ab36
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704800"
---
# <a name="applytohead-operation"></a><span data-ttu-id="4dd48-102">Operace ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="4dd48-102">ApplyToHead operation</span></span>

<span data-ttu-id="4dd48-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4dd48-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4dd48-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4dd48-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4dd48-105">Použije operaci na první prvek pole.</span><span class="sxs-lookup"><span data-stu-id="4dd48-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="4dd48-106">Popis</span><span class="sxs-lookup"><span data-stu-id="4dd48-106">Description</span></span>

<span data-ttu-id="4dd48-107">Daná operace `op` a pole cílů `targets` platí `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="4dd48-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="4dd48-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="4dd48-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="4dd48-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4dd48-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4dd48-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="4dd48-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4dd48-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="4dd48-111">targets : 'T[]</span></span>

<span data-ttu-id="4dd48-112">Pole cílů, na které se první použije `op` .</span><span class="sxs-lookup"><span data-stu-id="4dd48-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4dd48-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4dd48-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4dd48-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4dd48-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4dd48-115">'S</span><span class="sxs-lookup"><span data-stu-id="4dd48-115">'T</span></span>

<span data-ttu-id="4dd48-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="4dd48-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4dd48-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="4dd48-117">See Also</span></span>

- [<span data-ttu-id="4dd48-118">Microsoft. proApplyToHeadA. Canon.</span><span class="sxs-lookup"><span data-stu-id="4dd48-118">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="4dd48-119">Microsoft. proApplyToHeadC. Canon.</span><span class="sxs-lookup"><span data-stu-id="4dd48-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="4dd48-120">Microsoft. proApplyToHeadCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="4dd48-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)