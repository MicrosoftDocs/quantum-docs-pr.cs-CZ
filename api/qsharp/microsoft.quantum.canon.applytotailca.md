---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Operace ApplyToTailCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 4c702a9d310adae7a4ec404f3cf12893547623b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841198"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="b215e-102">Operace ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="b215e-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="b215e-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b215e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b215e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b215e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b215e-105">Použije operaci na poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="b215e-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b215e-106">Popis</span><span class="sxs-lookup"><span data-stu-id="b215e-106">Description</span></span>

<span data-ttu-id="b215e-107">Daná operace `op` a pole cílů `targets` platí `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="b215e-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="b215e-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="b215e-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="b215e-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="b215e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b215e-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="b215e-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="b215e-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="b215e-111">targets : 'T[]</span></span>

<span data-ttu-id="b215e-112">Pole cílů, z nichž poslední bude použito `op` .</span><span class="sxs-lookup"><span data-stu-id="b215e-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b215e-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b215e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b215e-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b215e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b215e-115">'S</span><span class="sxs-lookup"><span data-stu-id="b215e-115">'T</span></span>

<span data-ttu-id="b215e-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="b215e-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b215e-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="b215e-117">See Also</span></span>

- [<span data-ttu-id="b215e-118">Microsoft. proApplyToTail. Canon.</span><span class="sxs-lookup"><span data-stu-id="b215e-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="b215e-119">Microsoft. proApplyToTailA. Canon.</span><span class="sxs-lookup"><span data-stu-id="b215e-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="b215e-120">Microsoft. proApplyToTailC. Canon.</span><span class="sxs-lookup"><span data-stu-id="b215e-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)