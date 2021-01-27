---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: Operace ApplyToMost
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a3918233e101f3d8956601dcc7d85edcf6196ac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850594"
---
# <a name="applytomost-operation"></a><span data-ttu-id="ac7cf-102">Operace ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="ac7cf-102">ApplyToMost operation</span></span>

<span data-ttu-id="ac7cf-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ac7cf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ac7cf-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac7cf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac7cf-105">Aplikuje operaci na všechny, ale na poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="ac7cf-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="ac7cf-106">Popis</span><span class="sxs-lookup"><span data-stu-id="ac7cf-106">Description</span></span>

<span data-ttu-id="ac7cf-107">Daná operace `op` a pole cílů `targets` platí `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="ac7cf-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="ac7cf-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="ac7cf-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="ac7cf-109">op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac7cf-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ac7cf-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="ac7cf-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ac7cf-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="ac7cf-111">targets : 'T[]</span></span>

<span data-ttu-id="ac7cf-112">Pole cílů, z nichž všechny kromě posledního budou aplikovány na `op` .</span><span class="sxs-lookup"><span data-stu-id="ac7cf-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ac7cf-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac7cf-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ac7cf-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ac7cf-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ac7cf-115">'S</span><span class="sxs-lookup"><span data-stu-id="ac7cf-115">'T</span></span>

<span data-ttu-id="ac7cf-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="ac7cf-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="ac7cf-117">Příklad</span><span class="sxs-lookup"><span data-stu-id="ac7cf-117">Example</span></span>

<span data-ttu-id="ac7cf-118">Následující fragmenty Q # jsou ekvivalentní:</span><span class="sxs-lookup"><span data-stu-id="ac7cf-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToMost(ApplyCNOTChain, register);
ApplyCNOTChain(Most(register));
```

## <a name="see-also"></a><span data-ttu-id="ac7cf-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="ac7cf-119">See Also</span></span>

- [<span data-ttu-id="ac7cf-120">Microsoft. proApplyToMostA. Canon.</span><span class="sxs-lookup"><span data-stu-id="ac7cf-120">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="ac7cf-121">Microsoft. proApplyToMostC. Canon.</span><span class="sxs-lookup"><span data-stu-id="ac7cf-121">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="ac7cf-122">Microsoft. proApplyToMostCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="ac7cf-122">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)