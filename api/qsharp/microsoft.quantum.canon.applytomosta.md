---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: Operace ApplyToMostA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: eb793b3d6bc1f75a14e97420d36d0aea3038e0f5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850569"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="23a68-102">Operace ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="23a68-102">ApplyToMostA operation</span></span>

<span data-ttu-id="23a68-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="23a68-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="23a68-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="23a68-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="23a68-105">Aplikuje operaci na všechny, ale na poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="23a68-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="23a68-106">Popis</span><span class="sxs-lookup"><span data-stu-id="23a68-106">Description</span></span>

<span data-ttu-id="23a68-107">Daná operace `op` a pole cílů `targets` platí `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="23a68-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="23a68-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="23a68-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="23a68-109">op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="23a68-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="23a68-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="23a68-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="23a68-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="23a68-111">targets : 'T[]</span></span>

<span data-ttu-id="23a68-112">Pole cílů, z nichž všechny kromě posledního budou aplikovány na `op` .</span><span class="sxs-lookup"><span data-stu-id="23a68-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="23a68-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="23a68-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="23a68-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="23a68-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="23a68-115">'S</span><span class="sxs-lookup"><span data-stu-id="23a68-115">'T</span></span>

<span data-ttu-id="23a68-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="23a68-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="23a68-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="23a68-117">See Also</span></span>

- [<span data-ttu-id="23a68-118">Microsoft. proApplyToMost. Canon.</span><span class="sxs-lookup"><span data-stu-id="23a68-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="23a68-119">Microsoft. proApplyToMostC. Canon.</span><span class="sxs-lookup"><span data-stu-id="23a68-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="23a68-120">Microsoft. proApplyToMostCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="23a68-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)