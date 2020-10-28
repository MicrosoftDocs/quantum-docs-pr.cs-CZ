---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: Operace ApplyIfElseBCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 0ebd086f4c8166a8d6b593200b0a3354c1420c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705328"
---
# <a name="applyifelsebca-operation"></a><span data-ttu-id="742fb-102">Operace ApplyIfElseBCA</span><span class="sxs-lookup"><span data-stu-id="742fb-102">ApplyIfElseBCA operation</span></span>

<span data-ttu-id="742fb-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="742fb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="742fb-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="742fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="742fb-105">Aplikuje jednu ze dvou jednotkových operací v závislosti na hodnotě klasického bitu.</span><span class="sxs-lookup"><span data-stu-id="742fb-105">Applies one of two unitary operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="742fb-106">Popis</span><span class="sxs-lookup"><span data-stu-id="742fb-106">Description</span></span>

<span data-ttu-id="742fb-107">V případě bitu `bit` použije operaci `trueOp` s `trueInput` jako vstup `bit` , pokud je `true` , a platí, `falseOp(falseInput)` kdy `bit` je `false` .</span><span class="sxs-lookup"><span data-stu-id="742fb-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="742fb-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="742fb-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="742fb-109">bitová hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="742fb-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="742fb-110">Logická hodnota, která určuje, zda `trueOp` nebo `falseOp` je použita.</span><span class="sxs-lookup"><span data-stu-id="742fb-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit-adj--ctl"></a><span data-ttu-id="742fb-111">trueOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="742fb-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="742fb-112">Jednotná operace, která se má `bit` použít `true` , pokud je.</span><span class="sxs-lookup"><span data-stu-id="742fb-112">The unitary operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="742fb-113">trueInput: 'T</span><span class="sxs-lookup"><span data-stu-id="742fb-113">trueInput : 'T</span></span>

<span data-ttu-id="742fb-114">Vstup, který má být k dispozici, `trueOp` Když `bit` je `true` .</span><span class="sxs-lookup"><span data-stu-id="742fb-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit-adj--ctl"></a><span data-ttu-id="742fb-115">falseOp: ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="742fb-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="742fb-116">Jednotná operace, která se má `bit` použít `false` , pokud je.</span><span class="sxs-lookup"><span data-stu-id="742fb-116">The unitary operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="742fb-117">falseInput: ' U</span><span class="sxs-lookup"><span data-stu-id="742fb-117">falseInput : 'U</span></span>

<span data-ttu-id="742fb-118">Vstup, který má být k dispozici, `falseOp` Když `bit` je `false` .</span><span class="sxs-lookup"><span data-stu-id="742fb-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="742fb-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="742fb-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="742fb-120">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="742fb-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="742fb-121">'S</span><span class="sxs-lookup"><span data-stu-id="742fb-121">'T</span></span>

<span data-ttu-id="742fb-122">Vstupní typ operace `trueOp` , která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="742fb-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="742fb-123">U</span><span class="sxs-lookup"><span data-stu-id="742fb-123">'U</span></span>

<span data-ttu-id="742fb-124">Vstupní typ operace `falseOp` , která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="742fb-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="742fb-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="742fb-125">See Also</span></span>

- [<span data-ttu-id="742fb-126">Microsoft. proApplyIfZero. Canon.</span><span class="sxs-lookup"><span data-stu-id="742fb-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="742fb-127">Microsoft. proApplyIfOne. Canon.</span><span class="sxs-lookup"><span data-stu-id="742fb-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="742fb-128">Microsoft. proApplyIfElseRC. Canon.</span><span class="sxs-lookup"><span data-stu-id="742fb-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="742fb-129">Microsoft. proApplyIfElseRA. Canon.</span><span class="sxs-lookup"><span data-stu-id="742fb-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="742fb-130">Microsoft. proApplyIfElseRCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="742fb-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)