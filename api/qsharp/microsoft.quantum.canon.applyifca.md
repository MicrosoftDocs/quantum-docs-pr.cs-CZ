---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: Operace ApplyIfCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: 9057c79622f15a082963d94fc261664e00322feb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705352"
---
# <a name="applyifca-operation"></a><span data-ttu-id="3456d-102">Operace ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="3456d-102">ApplyIfCA operation</span></span>

<span data-ttu-id="3456d-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3456d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3456d-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3456d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3456d-105">Aplikuje jednotnou operaci s podmíněným klasickým bitem.</span><span class="sxs-lookup"><span data-stu-id="3456d-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="3456d-106">Popis</span><span class="sxs-lookup"><span data-stu-id="3456d-106">Description</span></span>

<span data-ttu-id="3456d-107">`op`Pokud je zadaná operace a bitová hodnota `bit` , platí `op` pro `target` if `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="3456d-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="3456d-108">`false`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="3456d-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="3456d-109">Přípona `CA` označuje, že operace, která se má použít, je jednotná (přivedená a přiléhající).</span><span class="sxs-lookup"><span data-stu-id="3456d-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="3456d-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="3456d-110">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="3456d-111">op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL a ADJ</span><span class="sxs-lookup"><span data-stu-id="3456d-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="3456d-112">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="3456d-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="3456d-113">bitová hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3456d-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3456d-114">logická hodnota, která určuje, zda je použita možnost op.</span><span class="sxs-lookup"><span data-stu-id="3456d-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="3456d-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="3456d-115">target : 'T</span></span>

<span data-ttu-id="3456d-116">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="3456d-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3456d-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3456d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3456d-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="3456d-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3456d-119">'S</span><span class="sxs-lookup"><span data-stu-id="3456d-119">'T</span></span>

<span data-ttu-id="3456d-120">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="3456d-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="3456d-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="3456d-121">See Also</span></span>

- [<span data-ttu-id="3456d-122">Microsoft. proApplyIfC. Canon.</span><span class="sxs-lookup"><span data-stu-id="3456d-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="3456d-123">Microsoft. proApplyIfA. Canon.</span><span class="sxs-lookup"><span data-stu-id="3456d-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="3456d-124">Microsoft. proApplyIfCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="3456d-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)