---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: Operace ApplyToMost
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2c6c8873859439e71436f6beb0de40dfd1e21f43
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704776"
---
# <a name="applytomost-operation"></a><span data-ttu-id="abb0f-102">Operace ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="abb0f-102">ApplyToMost operation</span></span>

<span data-ttu-id="abb0f-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="abb0f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="abb0f-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="abb0f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="abb0f-105">Aplikuje operaci na všechny, ale na poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="abb0f-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="abb0f-106">Popis</span><span class="sxs-lookup"><span data-stu-id="abb0f-106">Description</span></span>

<span data-ttu-id="abb0f-107">Daná operace `op` a pole cílů `targets` platí `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="abb0f-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="abb0f-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="abb0f-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="abb0f-109">op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="abb0f-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="abb0f-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="abb0f-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="abb0f-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="abb0f-111">targets : 'T[]</span></span>

<span data-ttu-id="abb0f-112">Pole cílů, z nichž všechny kromě posledního budou aplikovány na `op` .</span><span class="sxs-lookup"><span data-stu-id="abb0f-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="abb0f-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="abb0f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="abb0f-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="abb0f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="abb0f-115">'S</span><span class="sxs-lookup"><span data-stu-id="abb0f-115">'T</span></span>

<span data-ttu-id="abb0f-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="abb0f-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="abb0f-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="abb0f-117">See Also</span></span>

- [<span data-ttu-id="abb0f-118">Microsoft. proApplyToMostA. Canon.</span><span class="sxs-lookup"><span data-stu-id="abb0f-118">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="abb0f-119">Microsoft. proApplyToMostC. Canon.</span><span class="sxs-lookup"><span data-stu-id="abb0f-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="abb0f-120">Microsoft. proApplyToMostCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="abb0f-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)