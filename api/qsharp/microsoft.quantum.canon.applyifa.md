---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: Operace ApplyIfA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: 279a069176ee24ed83406f72170462bf58c790d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705361"
---
# <a name="applyifa-operation"></a><span data-ttu-id="7ffe8-102">Operace ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="7ffe8-102">ApplyIfA operation</span></span>

<span data-ttu-id="7ffe8-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7ffe8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7ffe8-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7ffe8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7ffe8-105">Aplikuje v klasickém bitu operaci s sousedním objektem.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="7ffe8-106">Popis</span><span class="sxs-lookup"><span data-stu-id="7ffe8-106">Description</span></span>

<span data-ttu-id="7ffe8-107">`op`Pokud je zadaná operace a bitová hodnota `bit` , platí `op` pro `target` if `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="7ffe8-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="7ffe8-108">`false`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="7ffe8-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="7ffe8-109">Přípona `A` označuje, že operace, která se má použít, je sousední.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="7ffe8-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="7ffe8-110">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="7ffe8-111">op: t => ADJ. [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7ffe8-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7ffe8-112">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="7ffe8-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="7ffe8-113">bitová hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7ffe8-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7ffe8-114">logická hodnota, která určuje, zda je použita možnost op.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="7ffe8-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="7ffe8-115">target : 'T</span></span>

<span data-ttu-id="7ffe8-116">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="7ffe8-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7ffe8-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7ffe8-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7ffe8-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7ffe8-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7ffe8-119">'S</span><span class="sxs-lookup"><span data-stu-id="7ffe8-119">'T</span></span>

<span data-ttu-id="7ffe8-120">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ffe8-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="7ffe8-121">See Also</span></span>

- [<span data-ttu-id="7ffe8-122">Microsoft. proApplyIfC. Canon.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="7ffe8-123">Microsoft. proApplyIfA. Canon.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="7ffe8-124">Microsoft. proApplyIfCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="7ffe8-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)