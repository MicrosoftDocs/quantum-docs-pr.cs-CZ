---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: Operace ApplyToTailA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 5ca22be7a38d466f9413977de663f10606171dea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841170"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="86942-102">Operace ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="86942-102">ApplyToTailA operation</span></span>

<span data-ttu-id="86942-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="86942-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="86942-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="86942-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="86942-105">Použije operaci na poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="86942-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="86942-106">Popis</span><span class="sxs-lookup"><span data-stu-id="86942-106">Description</span></span>

<span data-ttu-id="86942-107">Daná operace `op` a pole cílů `targets` platí `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="86942-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="86942-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="86942-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="86942-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="86942-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="86942-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="86942-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="86942-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="86942-111">targets : 'T[]</span></span>

<span data-ttu-id="86942-112">Pole cílů, z nichž poslední bude použito `op` .</span><span class="sxs-lookup"><span data-stu-id="86942-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="86942-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="86942-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="86942-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="86942-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="86942-115">'S</span><span class="sxs-lookup"><span data-stu-id="86942-115">'T</span></span>

<span data-ttu-id="86942-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="86942-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="86942-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="86942-117">See Also</span></span>

- [<span data-ttu-id="86942-118">Microsoft. proApplyToTail. Canon.</span><span class="sxs-lookup"><span data-stu-id="86942-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="86942-119">Microsoft. proApplyToTailC. Canon.</span><span class="sxs-lookup"><span data-stu-id="86942-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="86942-120">Microsoft. proApplyToTailCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="86942-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)