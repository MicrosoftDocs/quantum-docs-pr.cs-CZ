---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: Operace ApplyToRestC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 55e534b7b7673f300b607a8213418c45c8c7c92c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704697"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="e6e88-102">Operace ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="e6e88-102">ApplyToRestC operation</span></span>

<span data-ttu-id="e6e88-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e6e88-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e6e88-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e6e88-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e6e88-105">Aplikuje operaci na všechny, ale na první prvek pole.</span><span class="sxs-lookup"><span data-stu-id="e6e88-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="e6e88-106">Popis</span><span class="sxs-lookup"><span data-stu-id="e6e88-106">Description</span></span>

<span data-ttu-id="e6e88-107">Daná operace `op` a pole cílů `targets` platí `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="e6e88-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="e6e88-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="e6e88-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="e6e88-109">op: t [] [=> CTL](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6e88-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="e6e88-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="e6e88-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e6e88-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="e6e88-111">targets : 'T[]</span></span>

<span data-ttu-id="e6e88-112">Pole cílů, z nichž všechny kromě prvního budou aplikovány na `op` .</span><span class="sxs-lookup"><span data-stu-id="e6e88-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e6e88-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6e88-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e6e88-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e6e88-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e6e88-115">'S</span><span class="sxs-lookup"><span data-stu-id="e6e88-115">'T</span></span>

<span data-ttu-id="e6e88-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="e6e88-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6e88-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="e6e88-117">See Also</span></span>

- [<span data-ttu-id="e6e88-118">Microsoft. proApplyToRest. Canon.</span><span class="sxs-lookup"><span data-stu-id="e6e88-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="e6e88-119">Microsoft. proApplyToRestA. Canon.</span><span class="sxs-lookup"><span data-stu-id="e6e88-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="e6e88-120">Microsoft. proApplyToRestCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="e6e88-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)