---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: Operace ApplyToMostA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 7c226de9b2c99d124c467175dfe65a60a89d4332
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208495"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="6b35f-102">Operace ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="6b35f-102">ApplyToMostA operation</span></span>

<span data-ttu-id="6b35f-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6b35f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6b35f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b35f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b35f-105">Aplikuje operaci na všechny, ale na poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="6b35f-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="6b35f-106">Popis</span><span class="sxs-lookup"><span data-stu-id="6b35f-106">Description</span></span>

<span data-ttu-id="6b35f-107">Daná operace `op` a pole cílů `targets` platí `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="6b35f-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="6b35f-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="6b35f-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="6b35f-109">op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="6b35f-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6b35f-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="6b35f-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="6b35f-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="6b35f-111">targets : 'T[]</span></span>

<span data-ttu-id="6b35f-112">Pole cílů, z nichž všechny kromě posledního budou aplikovány na `op` .</span><span class="sxs-lookup"><span data-stu-id="6b35f-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b35f-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b35f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6b35f-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6b35f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6b35f-115">'S</span><span class="sxs-lookup"><span data-stu-id="6b35f-115">'T</span></span>

<span data-ttu-id="6b35f-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="6b35f-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b35f-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="6b35f-117">See Also</span></span>

- [<span data-ttu-id="6b35f-118">Microsoft. proApplyToMost. Canon.</span><span class="sxs-lookup"><span data-stu-id="6b35f-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="6b35f-119">Microsoft. proApplyToMostC. Canon.</span><span class="sxs-lookup"><span data-stu-id="6b35f-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="6b35f-120">Microsoft. proApplyToMostCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="6b35f-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)