---
uid: Microsoft.Quantum.Canon.ApplyIfElseRA
title: Operace ApplyIfElseRA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical result.
ms.openlocfilehash: 0a7683adfa15f787f96c7ae55f94e2c52426df75
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845019"
---
# <a name="applyifelsera-operation"></a><span data-ttu-id="0b46b-102">Operace ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="0b46b-102">ApplyIfElseRA operation</span></span>

<span data-ttu-id="0b46b-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0b46b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0b46b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b46b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b46b-105">Aplikuje jednu ze dvou sousedících operací v závislosti na hodnotě klasického výsledku.</span><span class="sxs-lookup"><span data-stu-id="0b46b-105">Applies one of two adjointable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj), zeroInput : 'T), (oneOp : ('U => Unit is Adj), oneInput : 'U)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="0b46b-106">Popis</span><span class="sxs-lookup"><span data-stu-id="0b46b-106">Description</span></span>

<span data-ttu-id="0b46b-107">Výsledkem `result` je, že použije operaci `zeroOp` s `zeroInput` jako vstup `result` , pokud je rovna `Zero` , a platí při použití `oneOp(oneInput)` `result == One` .</span><span class="sxs-lookup"><span data-stu-id="0b46b-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="0b46b-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="0b46b-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="0b46b-109">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="0b46b-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="0b46b-110">Výsledek měření použitý k určení, zda `zeroOp` nebo `oneOp` je použit.</span><span class="sxs-lookup"><span data-stu-id="0b46b-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-adj"></a><span data-ttu-id="0b46b-111">zeroOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="0b46b-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="0b46b-112">Operace sousedících operací, která má být použita v případě `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="0b46b-112">The adjointable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="0b46b-113">zeroInput: 'T</span><span class="sxs-lookup"><span data-stu-id="0b46b-113">zeroInput : 'T</span></span>

<span data-ttu-id="0b46b-114">Vstup, který má být k dispozici v `zeroOp` případě `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="0b46b-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-adj"></a><span data-ttu-id="0b46b-115">oneOp: jednotka U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="0b46b-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="0b46b-116">Operace sousedících operací, která má být použita v případě `result == One` .</span><span class="sxs-lookup"><span data-stu-id="0b46b-116">The adjointable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="0b46b-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="0b46b-117">oneInput : 'U</span></span>

<span data-ttu-id="0b46b-118">Vstup, který má být k dispozici v `oneOp` případě `result == One` .</span><span class="sxs-lookup"><span data-stu-id="0b46b-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0b46b-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0b46b-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0b46b-120">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="0b46b-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0b46b-121">'S</span><span class="sxs-lookup"><span data-stu-id="0b46b-121">'T</span></span>

<span data-ttu-id="0b46b-122">Vstupní typ operace `zeroOp` , která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="0b46b-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="0b46b-123">U</span><span class="sxs-lookup"><span data-stu-id="0b46b-123">'U</span></span>

<span data-ttu-id="0b46b-124">Vstupní typ operace `oneOp` , která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="0b46b-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b46b-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="0b46b-125">See Also</span></span>

- [<span data-ttu-id="0b46b-126">Microsoft. proApplyIfZero. Canon.</span><span class="sxs-lookup"><span data-stu-id="0b46b-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="0b46b-127">Microsoft. proApplyIfOne. Canon.</span><span class="sxs-lookup"><span data-stu-id="0b46b-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="0b46b-128">Microsoft. proApplyIfElseRC. Canon.</span><span class="sxs-lookup"><span data-stu-id="0b46b-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="0b46b-129">Microsoft. proApplyIfElseRA. Canon.</span><span class="sxs-lookup"><span data-stu-id="0b46b-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="0b46b-130">Microsoft. proApplyIfElseRCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="0b46b-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)