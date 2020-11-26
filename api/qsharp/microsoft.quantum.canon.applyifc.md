---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: Operace ApplyIfC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: 35430cb7cf491965b7b69ace6d3f41599dbadd51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218712"
---
# <a name="applyifc-operation"></a><span data-ttu-id="8002c-102">Operace ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="8002c-102">ApplyIfC operation</span></span>

<span data-ttu-id="8002c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8002c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8002c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8002c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8002c-105">Aplikuje naovladatelné operace s podmíněným klasickým bitem.</span><span class="sxs-lookup"><span data-stu-id="8002c-105">Applies a controllable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="8002c-106">Popis</span><span class="sxs-lookup"><span data-stu-id="8002c-106">Description</span></span>

<span data-ttu-id="8002c-107">`op`Pokud je zadaná operace a bitová hodnota `bit` , platí `op` pro `target` if `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="8002c-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="8002c-108">`false`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="8002c-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="8002c-109">Přípona `C` označuje, že operace, která se má použít, je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="8002c-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="8002c-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="8002c-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="8002c-111">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="8002c-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8002c-112">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="8002c-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="8002c-113">bitová hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8002c-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8002c-114">logická hodnota, která určuje, zda je použita možnost op.</span><span class="sxs-lookup"><span data-stu-id="8002c-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="8002c-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="8002c-115">target : 'T</span></span>

<span data-ttu-id="8002c-116">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="8002c-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8002c-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8002c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8002c-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8002c-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8002c-119">'S</span><span class="sxs-lookup"><span data-stu-id="8002c-119">'T</span></span>

<span data-ttu-id="8002c-120">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="8002c-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8002c-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="8002c-121">See Also</span></span>

- [<span data-ttu-id="8002c-122">Microsoft. proApplyIfC. Canon.</span><span class="sxs-lookup"><span data-stu-id="8002c-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="8002c-123">Microsoft. proApplyIfA. Canon.</span><span class="sxs-lookup"><span data-stu-id="8002c-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="8002c-124">Microsoft. proApplyIfCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="8002c-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)