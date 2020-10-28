---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: Operace ApplyToMostA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 994cada2952809dc84a70b76dc4ede8286c89855
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704761"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="8ae76-102">Operace ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="8ae76-102">ApplyToMostA operation</span></span>

<span data-ttu-id="8ae76-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8ae76-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8ae76-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8ae76-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8ae76-105">Aplikuje operaci na všechny, ale na poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="8ae76-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="8ae76-106">Popis</span><span class="sxs-lookup"><span data-stu-id="8ae76-106">Description</span></span>

<span data-ttu-id="8ae76-107">Daná operace `op` a pole cílů `targets` platí `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="8ae76-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="8ae76-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="8ae76-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="8ae76-109">op: t [] => ADJ. [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ae76-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="8ae76-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="8ae76-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="8ae76-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="8ae76-111">targets : 'T[]</span></span>

<span data-ttu-id="8ae76-112">Pole cílů, z nichž všechny kromě posledního budou aplikovány na `op` .</span><span class="sxs-lookup"><span data-stu-id="8ae76-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ae76-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ae76-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8ae76-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8ae76-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8ae76-115">'S</span><span class="sxs-lookup"><span data-stu-id="8ae76-115">'T</span></span>

<span data-ttu-id="8ae76-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="8ae76-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ae76-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="8ae76-117">See Also</span></span>

- [<span data-ttu-id="8ae76-118">Microsoft. proApplyToMost. Canon.</span><span class="sxs-lookup"><span data-stu-id="8ae76-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="8ae76-119">Microsoft. proApplyToMostC. Canon.</span><span class="sxs-lookup"><span data-stu-id="8ae76-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="8ae76-120">Microsoft. proApplyToMostCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="8ae76-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)