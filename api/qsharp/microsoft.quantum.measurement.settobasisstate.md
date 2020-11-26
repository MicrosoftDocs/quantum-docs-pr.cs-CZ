---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Operace SetToBasisState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: 2612bfe488c830abd835be89b2f8ea6795abf675
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194147"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="6c547-102">Operace SetToBasisState</span><span class="sxs-lookup"><span data-stu-id="6c547-102">SetToBasisState operation</span></span>

<span data-ttu-id="6c547-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="6c547-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="6c547-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6c547-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6c547-105">Nastaví qubit na daný výpočetní stav na základě měření qubit a v případě potřeby použije bitovou překlopení.</span><span class="sxs-lookup"><span data-stu-id="6c547-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="6c547-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6c547-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="6c547-107">požadováno: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="6c547-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="6c547-108">Základní stav, na který má být qubit nastaven.</span><span class="sxs-lookup"><span data-stu-id="6c547-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6c547-109">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6c547-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6c547-110">Qubit, jehož stav má být nastaven.</span><span class="sxs-lookup"><span data-stu-id="6c547-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6c547-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6c547-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6c547-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="6c547-112">Remarks</span></span>

<span data-ttu-id="6c547-113">Jako neutrální v této operaci se volá `M(q)` hned po `SetToBasisState(result, q)` návratu `result` .</span><span class="sxs-lookup"><span data-stu-id="6c547-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>