---
uid: Microsoft.Quantum.Canon.ApplyIfElseRCA
title: Operace ApplyIfElseRCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical result.
ms.openlocfilehash: c48d75323f036ebce1a316382a05cd2578db47a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705280"
---
# <a name="applyifelserca-operation"></a><span data-ttu-id="f9af1-102">Operace ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="f9af1-102">ApplyIfElseRCA operation</span></span>

<span data-ttu-id="f9af1-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f9af1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f9af1-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f9af1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f9af1-105">Aplikuje jednu ze dvou jednotkových operací v závislosti na hodnotě klasického výsledku.</span><span class="sxs-lookup"><span data-stu-id="f9af1-105">Applies one of two unitary operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRCA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj + Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Adj + Ctl), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="f9af1-106">Popis</span><span class="sxs-lookup"><span data-stu-id="f9af1-106">Description</span></span>

<span data-ttu-id="f9af1-107">Výsledkem `result` je, že použije operaci `zeroOp` s `zeroInput` jako vstup `result` , pokud je rovna `Zero` , a platí při použití `oneOp(oneInput)` `result == One` .</span><span class="sxs-lookup"><span data-stu-id="f9af1-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="f9af1-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="f9af1-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="f9af1-109">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="f9af1-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="f9af1-110">Výsledek měření použitý k určení, zda `zeroOp` nebo `oneOp` je použit.</span><span class="sxs-lookup"><span data-stu-id="f9af1-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit-adj--ctl"></a><span data-ttu-id="f9af1-111">zeroOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="f9af1-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f9af1-112">Jednotná operace, která se má použít `result == Zero` , když.</span><span class="sxs-lookup"><span data-stu-id="f9af1-112">The unitary operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="f9af1-113">zeroInput: 'T</span><span class="sxs-lookup"><span data-stu-id="f9af1-113">zeroInput : 'T</span></span>

<span data-ttu-id="f9af1-114">Vstup, který má být k dispozici v `zeroOp` případě `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="f9af1-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit-adj--ctl"></a><span data-ttu-id="f9af1-115">oneOp: ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="f9af1-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f9af1-116">Jednotná operace, která se má použít `result == One` , když.</span><span class="sxs-lookup"><span data-stu-id="f9af1-116">The unitary operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="f9af1-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="f9af1-117">oneInput : 'U</span></span>

<span data-ttu-id="f9af1-118">Vstup, který má být k dispozici v `oneOp` případě `result == One` .</span><span class="sxs-lookup"><span data-stu-id="f9af1-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f9af1-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9af1-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f9af1-120">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f9af1-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f9af1-121">'S</span><span class="sxs-lookup"><span data-stu-id="f9af1-121">'T</span></span>

<span data-ttu-id="f9af1-122">Vstupní typ operace `zeroOp` , která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="f9af1-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="f9af1-123">U</span><span class="sxs-lookup"><span data-stu-id="f9af1-123">'U</span></span>

<span data-ttu-id="f9af1-124">Vstupní typ operace `oneOp` , která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="f9af1-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9af1-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="f9af1-125">See Also</span></span>

- [<span data-ttu-id="f9af1-126">Microsoft. proApplyIfZero. Canon.</span><span class="sxs-lookup"><span data-stu-id="f9af1-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="f9af1-127">Microsoft. proApplyIfOne. Canon.</span><span class="sxs-lookup"><span data-stu-id="f9af1-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="f9af1-128">Microsoft. proApplyIfElseRC. Canon.</span><span class="sxs-lookup"><span data-stu-id="f9af1-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="f9af1-129">Microsoft. proApplyIfElseRA. Canon.</span><span class="sxs-lookup"><span data-stu-id="f9af1-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="f9af1-130">Microsoft. proApplyIfElseRCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="f9af1-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)