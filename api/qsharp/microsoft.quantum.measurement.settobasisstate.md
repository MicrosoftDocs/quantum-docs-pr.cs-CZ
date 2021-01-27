---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Operace SetToBasisState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: dfa054360a5e82b7ae6ec5a6d52e7d5fe566f42e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854626"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="8d62d-102">Operace SetToBasisState</span><span class="sxs-lookup"><span data-stu-id="8d62d-102">SetToBasisState operation</span></span>

<span data-ttu-id="8d62d-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="8d62d-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="8d62d-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8d62d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8d62d-105">Nastaví qubit na daný výpočetní stav na základě měření qubit a v případě potřeby použije bitovou překlopení.</span><span class="sxs-lookup"><span data-stu-id="8d62d-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="8d62d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8d62d-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="8d62d-107">požadováno: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="8d62d-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="8d62d-108">Základní stav, na který má být qubit nastaven.</span><span class="sxs-lookup"><span data-stu-id="8d62d-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8d62d-109">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8d62d-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8d62d-110">Qubit, jehož stav má být nastaven.</span><span class="sxs-lookup"><span data-stu-id="8d62d-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8d62d-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8d62d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8d62d-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="8d62d-112">Remarks</span></span>

<span data-ttu-id="8d62d-113">Jako neutrální v této operaci se volá `M(q)` hned po `SetToBasisState(result, q)` návratu `result` .</span><span class="sxs-lookup"><span data-stu-id="8d62d-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>