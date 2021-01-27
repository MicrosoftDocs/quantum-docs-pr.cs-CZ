---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: Operace ApplyIfElseBCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 3ed9d7cbf277f4c3acd0e6c3b5f920c3e140855d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844960"
---
# <a name="applyifelsebca-operation"></a><span data-ttu-id="b474d-102">Operace ApplyIfElseBCA</span><span class="sxs-lookup"><span data-stu-id="b474d-102">ApplyIfElseBCA operation</span></span>

<span data-ttu-id="b474d-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b474d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b474d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b474d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b474d-105">Aplikuje jednu ze dvou jednotkových operací v závislosti na hodnotě klasického bitu.</span><span class="sxs-lookup"><span data-stu-id="b474d-105">Applies one of two unitary operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b474d-106">Popis</span><span class="sxs-lookup"><span data-stu-id="b474d-106">Description</span></span>

<span data-ttu-id="b474d-107">V případě bitu `bit` použije operaci `trueOp` s `trueInput` jako vstup `bit` , pokud je `true` , a platí, `falseOp(falseInput)` kdy `bit` je `false` .</span><span class="sxs-lookup"><span data-stu-id="b474d-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="b474d-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="b474d-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="b474d-109">bitová hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b474d-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b474d-110">Logická hodnota, která určuje, zda `trueOp` nebo `falseOp` je použita.</span><span class="sxs-lookup"><span data-stu-id="b474d-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit--is-adj--ctl"></a><span data-ttu-id="b474d-111">trueOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="b474d-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b474d-112">Jednotná operace, která se má `bit` použít `true` , pokud je.</span><span class="sxs-lookup"><span data-stu-id="b474d-112">The unitary operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="b474d-113">trueInput: 'T</span><span class="sxs-lookup"><span data-stu-id="b474d-113">trueInput : 'T</span></span>

<span data-ttu-id="b474d-114">Vstup, který má být k dispozici, `trueOp` Když `bit` je `true` .</span><span class="sxs-lookup"><span data-stu-id="b474d-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit--is-adj--ctl"></a><span data-ttu-id="b474d-115">falseOp: "U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="b474d-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b474d-116">Jednotná operace, která se má `bit` použít `false` , pokud je.</span><span class="sxs-lookup"><span data-stu-id="b474d-116">The unitary operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="b474d-117">falseInput: ' U</span><span class="sxs-lookup"><span data-stu-id="b474d-117">falseInput : 'U</span></span>

<span data-ttu-id="b474d-118">Vstup, který má být k dispozici, `falseOp` Když `bit` je `false` .</span><span class="sxs-lookup"><span data-stu-id="b474d-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b474d-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b474d-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b474d-120">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b474d-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b474d-121">'S</span><span class="sxs-lookup"><span data-stu-id="b474d-121">'T</span></span>

<span data-ttu-id="b474d-122">Vstupní typ operace `trueOp` , která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="b474d-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="b474d-123">U</span><span class="sxs-lookup"><span data-stu-id="b474d-123">'U</span></span>

<span data-ttu-id="b474d-124">Vstupní typ operace `falseOp` , která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="b474d-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b474d-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="b474d-125">See Also</span></span>

- [<span data-ttu-id="b474d-126">Microsoft. proApplyIfZero. Canon.</span><span class="sxs-lookup"><span data-stu-id="b474d-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="b474d-127">Microsoft. proApplyIfOne. Canon.</span><span class="sxs-lookup"><span data-stu-id="b474d-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="b474d-128">Microsoft. proApplyIfElseRC. Canon.</span><span class="sxs-lookup"><span data-stu-id="b474d-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="b474d-129">Microsoft. proApplyIfElseRA. Canon.</span><span class="sxs-lookup"><span data-stu-id="b474d-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="b474d-130">Microsoft. proApplyIfElseRCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="b474d-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)