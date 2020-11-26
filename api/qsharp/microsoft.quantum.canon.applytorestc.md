---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: Operace ApplyToRestC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 779c3831b2027a58f97dae9609e96d4d98247da7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208189"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="48801-102">Operace ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="48801-102">ApplyToRestC operation</span></span>

<span data-ttu-id="48801-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="48801-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="48801-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="48801-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="48801-105">Aplikuje operaci na všechny, ale na první prvek pole.</span><span class="sxs-lookup"><span data-stu-id="48801-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="48801-106">Popis</span><span class="sxs-lookup"><span data-stu-id="48801-106">Description</span></span>

<span data-ttu-id="48801-107">Daná operace `op` a pole cílů `targets` platí `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="48801-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="48801-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="48801-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="48801-109">op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL.</span><span class="sxs-lookup"><span data-stu-id="48801-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="48801-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="48801-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="48801-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="48801-111">targets : 'T[]</span></span>

<span data-ttu-id="48801-112">Pole cílů, z nichž všechny kromě prvního budou aplikovány na `op` .</span><span class="sxs-lookup"><span data-stu-id="48801-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="48801-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="48801-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="48801-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="48801-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="48801-115">'S</span><span class="sxs-lookup"><span data-stu-id="48801-115">'T</span></span>

<span data-ttu-id="48801-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="48801-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="48801-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="48801-117">See Also</span></span>

- [<span data-ttu-id="48801-118">Microsoft. proApplyToRest. Canon.</span><span class="sxs-lookup"><span data-stu-id="48801-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="48801-119">Microsoft. proApplyToRestA. Canon.</span><span class="sxs-lookup"><span data-stu-id="48801-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="48801-120">Microsoft. proApplyToRestCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="48801-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)