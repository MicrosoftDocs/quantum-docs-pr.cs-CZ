---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: Operace ApplyIfElseRC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: 45bd0f46fb2e28c5c9aaa21cb7ec065baf279d2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705281"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="b40ce-102">Operace ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="b40ce-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="b40ce-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b40ce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b40ce-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b40ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b40ce-105">Aplikuje jednu ze dvou přizpůsobených operací v závislosti na hodnotě klasického výsledku.</span><span class="sxs-lookup"><span data-stu-id="b40ce-105">Applies one of two controllable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="b40ce-106">Popis</span><span class="sxs-lookup"><span data-stu-id="b40ce-106">Description</span></span>

<span data-ttu-id="b40ce-107">Výsledkem `result` je, že použije operaci `zeroOp` s `zeroInput` jako vstup `result` , pokud je rovna `Zero` , a platí při použití `oneOp(oneInput)` `result == One` .</span><span class="sxs-lookup"><span data-stu-id="b40ce-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="b40ce-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="b40ce-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="b40ce-109">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="b40ce-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="b40ce-110">Výsledek měření použitý k určení, zda `zeroOp` nebo `oneOp` je použit.</span><span class="sxs-lookup"><span data-stu-id="b40ce-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit-ctl"></a><span data-ttu-id="b40ce-111">zeroOp: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="b40ce-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="b40ce-112">Ověřitelné operace, která se má použít `result == Zero` , když.</span><span class="sxs-lookup"><span data-stu-id="b40ce-112">The controllable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="b40ce-113">zeroInput: 'T</span><span class="sxs-lookup"><span data-stu-id="b40ce-113">zeroInput : 'T</span></span>

<span data-ttu-id="b40ce-114">Vstup, který má být k dispozici v `zeroOp` případě `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="b40ce-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit-ctl"></a><span data-ttu-id="b40ce-115">oneOp: U [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="b40ce-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="b40ce-116">Ověřitelné operace, která se má použít `result == One` , když.</span><span class="sxs-lookup"><span data-stu-id="b40ce-116">The controllable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="b40ce-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="b40ce-117">oneInput : 'U</span></span>

<span data-ttu-id="b40ce-118">Vstup, který má být k dispozici v `oneOp` případě `result == One` .</span><span class="sxs-lookup"><span data-stu-id="b40ce-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b40ce-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b40ce-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b40ce-120">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b40ce-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b40ce-121">'S</span><span class="sxs-lookup"><span data-stu-id="b40ce-121">'T</span></span>

<span data-ttu-id="b40ce-122">Vstupní typ operace `zeroOp` , která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="b40ce-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="b40ce-123">U</span><span class="sxs-lookup"><span data-stu-id="b40ce-123">'U</span></span>

<span data-ttu-id="b40ce-124">Vstupní typ operace `oneOp` , která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="b40ce-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b40ce-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="b40ce-125">See Also</span></span>

- [<span data-ttu-id="b40ce-126">Microsoft. proApplyIfZero. Canon.</span><span class="sxs-lookup"><span data-stu-id="b40ce-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="b40ce-127">Microsoft. proApplyIfOne. Canon.</span><span class="sxs-lookup"><span data-stu-id="b40ce-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="b40ce-128">Microsoft. proApplyIfElseRC. Canon.</span><span class="sxs-lookup"><span data-stu-id="b40ce-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="b40ce-129">Microsoft. proApplyIfElseRA. Canon.</span><span class="sxs-lookup"><span data-stu-id="b40ce-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="b40ce-130">Microsoft. proApplyIfElseRCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="b40ce-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)