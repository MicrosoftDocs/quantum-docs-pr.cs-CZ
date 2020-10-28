---
uid: Microsoft.Quantum.Canon.ApplyIfElseB
title: Operace ApplyIfElseB
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseB
qsharp.summary: Applies one of two operations, depending on the value of a classical bit.
ms.openlocfilehash: 68c06a5141b9ff423c2d18adc3a9e162eed939f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705344"
---
# <a name="applyifelseb-operation"></a><span data-ttu-id="50e31-102">Operace ApplyIfElseB</span><span class="sxs-lookup"><span data-stu-id="50e31-102">ApplyIfElseB operation</span></span>

<span data-ttu-id="50e31-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="50e31-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="50e31-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50e31-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50e31-105">Aplikuje jednu ze dvou operací v závislosti na hodnotě klasického bitu.</span><span class="sxs-lookup"><span data-stu-id="50e31-105">Applies one of two operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseB<'T, 'U> (bit : Bool, (trueOp : ('T => Unit), trueInput : 'T), (falseOp : ('U => Unit), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="50e31-106">Popis</span><span class="sxs-lookup"><span data-stu-id="50e31-106">Description</span></span>

<span data-ttu-id="50e31-107">V případě bitu `bit` použije operaci `trueOp` s `trueInput` jako vstup `bit` , pokud je `true` , a platí, `falseOp(falseInput)` kdy `bit` je `false` .</span><span class="sxs-lookup"><span data-stu-id="50e31-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="50e31-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="50e31-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="50e31-109">bitová hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="50e31-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="50e31-110">Logická hodnota, která určuje, zda `trueOp` nebo `falseOp` je použita.</span><span class="sxs-lookup"><span data-stu-id="50e31-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit"></a><span data-ttu-id="50e31-111">trueOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50e31-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="50e31-112">Operace, která se má použít, pokud `bit` je `true` .</span><span class="sxs-lookup"><span data-stu-id="50e31-112">The operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="50e31-113">trueInput: 'T</span><span class="sxs-lookup"><span data-stu-id="50e31-113">trueInput : 'T</span></span>

<span data-ttu-id="50e31-114">Vstup, který má být k dispozici, `trueOp` Když `bit` je `true` .</span><span class="sxs-lookup"><span data-stu-id="50e31-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit"></a><span data-ttu-id="50e31-115">falseOp: [jednotka](xref:microsoft.quantum.lang-ref.unit) U =></span><span class="sxs-lookup"><span data-stu-id="50e31-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="50e31-116">Operace, která se má použít, pokud `bit` je `false` .</span><span class="sxs-lookup"><span data-stu-id="50e31-116">The operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="50e31-117">falseInput: ' U</span><span class="sxs-lookup"><span data-stu-id="50e31-117">falseInput : 'U</span></span>

<span data-ttu-id="50e31-118">Vstup, který má být k dispozici, `falseOp` Když `bit` je `false` .</span><span class="sxs-lookup"><span data-stu-id="50e31-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="50e31-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50e31-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="50e31-120">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="50e31-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="50e31-121">'S</span><span class="sxs-lookup"><span data-stu-id="50e31-121">'T</span></span>

<span data-ttu-id="50e31-122">Vstupní typ operace `trueOp` , která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="50e31-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="50e31-123">U</span><span class="sxs-lookup"><span data-stu-id="50e31-123">'U</span></span>

<span data-ttu-id="50e31-124">Vstupní typ operace `falseOp` , která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="50e31-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="50e31-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="50e31-125">See Also</span></span>

- [<span data-ttu-id="50e31-126">Microsoft. proApplyIfZero. Canon.</span><span class="sxs-lookup"><span data-stu-id="50e31-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="50e31-127">Microsoft. proApplyIfOne. Canon.</span><span class="sxs-lookup"><span data-stu-id="50e31-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="50e31-128">Microsoft. proApplyIfElseRC. Canon.</span><span class="sxs-lookup"><span data-stu-id="50e31-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="50e31-129">Microsoft. proApplyIfElseRA. Canon.</span><span class="sxs-lookup"><span data-stu-id="50e31-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="50e31-130">Microsoft. proApplyIfElseRCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="50e31-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)