---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: Operace ApplyToMostCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 797cbd835446f31b2df60dbb184f888e6d0356aa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704737"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="a9edc-102">Operace ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="a9edc-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="a9edc-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a9edc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a9edc-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9edc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9edc-105">Aplikuje operaci na všechny, ale na poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="a9edc-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="a9edc-106">Popis</span><span class="sxs-lookup"><span data-stu-id="a9edc-106">Description</span></span>

<span data-ttu-id="a9edc-107">Daná operace `op` a pole cílů `targets` platí `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="a9edc-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="a9edc-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="a9edc-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="a9edc-109">op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="a9edc-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a9edc-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="a9edc-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="a9edc-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="a9edc-111">targets : 'T[]</span></span>

<span data-ttu-id="a9edc-112">Pole cílů, z nichž všechny kromě posledního budou aplikovány na `op` .</span><span class="sxs-lookup"><span data-stu-id="a9edc-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a9edc-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9edc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a9edc-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a9edc-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a9edc-115">'S</span><span class="sxs-lookup"><span data-stu-id="a9edc-115">'T</span></span>

<span data-ttu-id="a9edc-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="a9edc-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9edc-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="a9edc-117">See Also</span></span>

- [<span data-ttu-id="a9edc-118">Microsoft. proApplyToMost. Canon.</span><span class="sxs-lookup"><span data-stu-id="a9edc-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="a9edc-119">Microsoft. proApplyToMostA. Canon.</span><span class="sxs-lookup"><span data-stu-id="a9edc-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="a9edc-120">Microsoft. proApplyToMostC. Canon.</span><span class="sxs-lookup"><span data-stu-id="a9edc-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)