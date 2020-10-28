---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Operace ApplyIf
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c8f6860a7a3b8af86b0edb048baccbf057dd245a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705360"
---
# <a name="applyif-operation"></a><span data-ttu-id="d8d82-102">Operace ApplyIf</span><span class="sxs-lookup"><span data-stu-id="d8d82-102">ApplyIf operation</span></span>

<span data-ttu-id="d8d82-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d8d82-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d8d82-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d8d82-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d8d82-105">Použije operaci s podmíněným klasickým bitem.</span><span class="sxs-lookup"><span data-stu-id="d8d82-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="d8d82-106">Popis</span><span class="sxs-lookup"><span data-stu-id="d8d82-106">Description</span></span>

<span data-ttu-id="d8d82-107">`op`Pokud je zadaná operace a bitová hodnota `bit` , platí `op` pro `target` if `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="d8d82-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="d8d82-108">`false`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="d8d82-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="d8d82-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="d8d82-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="d8d82-110">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d8d82-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d8d82-111">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="d8d82-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="d8d82-112">bitová hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d8d82-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d8d82-113">logická hodnota, která určuje, zda je použita možnost op.</span><span class="sxs-lookup"><span data-stu-id="d8d82-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="d8d82-114">cíl: t</span><span class="sxs-lookup"><span data-stu-id="d8d82-114">target : 'T</span></span>

<span data-ttu-id="d8d82-115">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="d8d82-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d8d82-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d8d82-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d8d82-117">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d8d82-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d8d82-118">'S</span><span class="sxs-lookup"><span data-stu-id="d8d82-118">'T</span></span>

<span data-ttu-id="d8d82-119">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="d8d82-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8d82-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="d8d82-120">See Also</span></span>

- [<span data-ttu-id="d8d82-121">Microsoft. proApplyIfC. Canon.</span><span class="sxs-lookup"><span data-stu-id="d8d82-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="d8d82-122">Microsoft. proApplyIfA. Canon.</span><span class="sxs-lookup"><span data-stu-id="d8d82-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="d8d82-123">Microsoft. proApplyIfCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="d8d82-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)