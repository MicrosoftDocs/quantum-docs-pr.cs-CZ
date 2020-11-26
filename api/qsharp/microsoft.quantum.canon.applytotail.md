---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: Operace ApplyToTail
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 6754d41e63ea0357487fa2f62bd9209843a93347
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207968"
---
# <a name="applytotail-operation"></a><span data-ttu-id="fe6cd-102">Operace ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="fe6cd-102">ApplyToTail operation</span></span>

<span data-ttu-id="fe6cd-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fe6cd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fe6cd-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe6cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe6cd-105">Použije operaci na poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="fe6cd-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="fe6cd-106">Popis</span><span class="sxs-lookup"><span data-stu-id="fe6cd-106">Description</span></span>

<span data-ttu-id="fe6cd-107">Daná operace `op` a pole cílů `targets` platí `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="fe6cd-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="fe6cd-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="fe6cd-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="fe6cd-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fe6cd-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fe6cd-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="fe6cd-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="fe6cd-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="fe6cd-111">targets : 'T[]</span></span>

<span data-ttu-id="fe6cd-112">Pole cílů, z nichž poslední bude použito `op` .</span><span class="sxs-lookup"><span data-stu-id="fe6cd-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fe6cd-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fe6cd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fe6cd-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="fe6cd-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fe6cd-115">'S</span><span class="sxs-lookup"><span data-stu-id="fe6cd-115">'T</span></span>

<span data-ttu-id="fe6cd-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="fe6cd-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe6cd-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="fe6cd-117">See Also</span></span>

- [<span data-ttu-id="fe6cd-118">Microsoft. proApplyToTailA. Canon.</span><span class="sxs-lookup"><span data-stu-id="fe6cd-118">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="fe6cd-119">Microsoft. proApplyToTailC. Canon.</span><span class="sxs-lookup"><span data-stu-id="fe6cd-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="fe6cd-120">Microsoft. proApplyToTailCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="fe6cd-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)