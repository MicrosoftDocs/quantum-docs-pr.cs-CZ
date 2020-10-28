---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: Operace ApplyToMostC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a5927f6b296dd50afec8979c8e8ac22979b8a082
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704744"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="c6e09-102">Operace ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="c6e09-102">ApplyToMostC operation</span></span>

<span data-ttu-id="c6e09-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c6e09-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c6e09-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c6e09-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c6e09-105">Aplikuje operaci na všechny, ale na poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="c6e09-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="c6e09-106">Popis</span><span class="sxs-lookup"><span data-stu-id="c6e09-106">Description</span></span>

<span data-ttu-id="c6e09-107">Daná operace `op` a pole cílů `targets` platí `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="c6e09-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="c6e09-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="c6e09-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="c6e09-109">op: t [] [=> CTL](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6e09-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c6e09-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="c6e09-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="c6e09-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="c6e09-111">targets : 'T[]</span></span>

<span data-ttu-id="c6e09-112">Pole cílů, z nichž všechny kromě posledního budou aplikovány na `op` .</span><span class="sxs-lookup"><span data-stu-id="c6e09-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c6e09-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6e09-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c6e09-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c6e09-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c6e09-115">'S</span><span class="sxs-lookup"><span data-stu-id="c6e09-115">'T</span></span>

<span data-ttu-id="c6e09-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="c6e09-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6e09-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="c6e09-117">See Also</span></span>

- [<span data-ttu-id="c6e09-118">Microsoft. proApplyToMost. Canon.</span><span class="sxs-lookup"><span data-stu-id="c6e09-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="c6e09-119">Microsoft. proApplyToMostA. Canon.</span><span class="sxs-lookup"><span data-stu-id="c6e09-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="c6e09-120">Microsoft. proApplyToMostCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="c6e09-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)