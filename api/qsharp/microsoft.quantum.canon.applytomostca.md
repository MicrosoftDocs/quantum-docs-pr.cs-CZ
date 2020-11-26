---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: Operace ApplyToMostCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2ce76d2a86665fbfa5f5d91df23220c7c80981e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208410"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="22b8c-102">Operace ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="22b8c-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="22b8c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="22b8c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="22b8c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="22b8c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="22b8c-105">Aplikuje operaci na všechny, ale na poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="22b8c-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="22b8c-106">Popis</span><span class="sxs-lookup"><span data-stu-id="22b8c-106">Description</span></span>

<span data-ttu-id="22b8c-107">Daná operace `op` a pole cílů `targets` platí `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="22b8c-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="22b8c-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="22b8c-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="22b8c-109">op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="22b8c-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="22b8c-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="22b8c-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="22b8c-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="22b8c-111">targets : 'T[]</span></span>

<span data-ttu-id="22b8c-112">Pole cílů, z nichž všechny kromě posledního budou aplikovány na `op` .</span><span class="sxs-lookup"><span data-stu-id="22b8c-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="22b8c-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="22b8c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="22b8c-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="22b8c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="22b8c-115">'S</span><span class="sxs-lookup"><span data-stu-id="22b8c-115">'T</span></span>

<span data-ttu-id="22b8c-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="22b8c-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="22b8c-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="22b8c-117">See Also</span></span>

- [<span data-ttu-id="22b8c-118">Microsoft. proApplyToMost. Canon.</span><span class="sxs-lookup"><span data-stu-id="22b8c-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="22b8c-119">Microsoft. proApplyToMostA. Canon.</span><span class="sxs-lookup"><span data-stu-id="22b8c-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="22b8c-120">Microsoft. proApplyToMostC. Canon.</span><span class="sxs-lookup"><span data-stu-id="22b8c-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)