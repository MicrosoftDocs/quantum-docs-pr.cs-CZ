---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: Operace ApplyToMostC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: af55093e44ce023c9e8b7e478730f4c527cf6d32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208461"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="d1118-102">Operace ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="d1118-102">ApplyToMostC operation</span></span>

<span data-ttu-id="d1118-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d1118-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d1118-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1118-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1118-105">Aplikuje operaci na všechny, ale na poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="d1118-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="d1118-106">Popis</span><span class="sxs-lookup"><span data-stu-id="d1118-106">Description</span></span>

<span data-ttu-id="d1118-107">Daná operace `op` a pole cílů `targets` platí `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="d1118-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d1118-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="d1118-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="d1118-109">op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL.</span><span class="sxs-lookup"><span data-stu-id="d1118-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="d1118-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="d1118-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d1118-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="d1118-111">targets : 'T[]</span></span>

<span data-ttu-id="d1118-112">Pole cílů, z nichž všechny kromě posledního budou aplikovány na `op` .</span><span class="sxs-lookup"><span data-stu-id="d1118-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d1118-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d1118-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d1118-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d1118-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d1118-115">'S</span><span class="sxs-lookup"><span data-stu-id="d1118-115">'T</span></span>

<span data-ttu-id="d1118-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="d1118-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1118-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="d1118-117">See Also</span></span>

- [<span data-ttu-id="d1118-118">Microsoft. proApplyToMost. Canon.</span><span class="sxs-lookup"><span data-stu-id="d1118-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="d1118-119">Microsoft. proApplyToMostA. Canon.</span><span class="sxs-lookup"><span data-stu-id="d1118-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="d1118-120">Microsoft. proApplyToMostCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="d1118-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)