---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: Operace ApplyIfCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b0ac469d6dea51951e0d9b2cfceb54253d4b4c5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209617"
---
# <a name="applyifca-operation"></a><span data-ttu-id="80825-102">Operace ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="80825-102">ApplyIfCA operation</span></span>

<span data-ttu-id="80825-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="80825-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="80825-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80825-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80825-105">Aplikuje jednotnou operaci s podmíněným klasickým bitem.</span><span class="sxs-lookup"><span data-stu-id="80825-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="80825-106">Popis</span><span class="sxs-lookup"><span data-stu-id="80825-106">Description</span></span>

<span data-ttu-id="80825-107">`op`Pokud je zadaná operace a bitová hodnota `bit` , platí `op` pro `target` if `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="80825-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="80825-108">`false`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="80825-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="80825-109">Přípona `CA` označuje, že operace, která se má použít, je jednotná (přivedená a přiléhající).</span><span class="sxs-lookup"><span data-stu-id="80825-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="80825-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="80825-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="80825-111">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="80825-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="80825-112">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="80825-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="80825-113">bitová hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="80825-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="80825-114">logická hodnota, která určuje, zda je použita možnost op.</span><span class="sxs-lookup"><span data-stu-id="80825-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="80825-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="80825-115">target : 'T</span></span>

<span data-ttu-id="80825-116">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="80825-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="80825-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80825-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="80825-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="80825-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="80825-119">'S</span><span class="sxs-lookup"><span data-stu-id="80825-119">'T</span></span>

<span data-ttu-id="80825-120">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="80825-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="80825-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="80825-121">See Also</span></span>

- [<span data-ttu-id="80825-122">Microsoft. proApplyIfC. Canon.</span><span class="sxs-lookup"><span data-stu-id="80825-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="80825-123">Microsoft. proApplyIfA. Canon.</span><span class="sxs-lookup"><span data-stu-id="80825-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="80825-124">Microsoft. proApplyIfCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="80825-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)