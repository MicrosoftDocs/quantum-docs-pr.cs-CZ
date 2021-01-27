---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: Operace ApplyToHead
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e627b467e9354e774c2ead8b89ddd3ff3a42ef7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841323"
---
# <a name="applytohead-operation"></a><span data-ttu-id="d7652-102">Operace ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="d7652-102">ApplyToHead operation</span></span>

<span data-ttu-id="d7652-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d7652-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d7652-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d7652-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d7652-105">Použije operaci na první prvek pole.</span><span class="sxs-lookup"><span data-stu-id="d7652-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="d7652-106">Popis</span><span class="sxs-lookup"><span data-stu-id="d7652-106">Description</span></span>

<span data-ttu-id="d7652-107">Daná operace `op` a pole cílů `targets` platí `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="d7652-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d7652-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="d7652-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="d7652-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7652-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d7652-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="d7652-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d7652-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="d7652-111">targets : 'T[]</span></span>

<span data-ttu-id="d7652-112">Pole cílů, na které se první použije `op` .</span><span class="sxs-lookup"><span data-stu-id="d7652-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d7652-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7652-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d7652-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d7652-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d7652-115">'S</span><span class="sxs-lookup"><span data-stu-id="d7652-115">'T</span></span>

<span data-ttu-id="d7652-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="d7652-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="d7652-117">Příklad</span><span class="sxs-lookup"><span data-stu-id="d7652-117">Example</span></span>

<span data-ttu-id="d7652-118">Následující fragmenty Q # jsou ekvivalentní:</span><span class="sxs-lookup"><span data-stu-id="d7652-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToHead(H, register);
H(Head(register));
```

## <a name="see-also"></a><span data-ttu-id="d7652-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="d7652-119">See Also</span></span>

- [<span data-ttu-id="d7652-120">Microsoft. proApplyToHeadA. Canon.</span><span class="sxs-lookup"><span data-stu-id="d7652-120">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="d7652-121">Microsoft. proApplyToHeadC. Canon.</span><span class="sxs-lookup"><span data-stu-id="d7652-121">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="d7652-122">Microsoft. proApplyToHeadCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="d7652-122">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)