---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Operace SetToBasisState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708938"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="3b257-102">Operace SetToBasisState</span><span class="sxs-lookup"><span data-stu-id="3b257-102">SetToBasisState operation</span></span>

<span data-ttu-id="3b257-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="3b257-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="3b257-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b257-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b257-105">Nastaví qubit na daný výpočetní stav na základě měření qubit a v případě potřeby použije bitovou překlopení.</span><span class="sxs-lookup"><span data-stu-id="3b257-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="3b257-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3b257-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="3b257-107">požadováno: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="3b257-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="3b257-108">Základní stav, na který má být qubit nastaven.</span><span class="sxs-lookup"><span data-stu-id="3b257-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="3b257-109">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3b257-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3b257-110">Qubit, jehož stav má být nastaven.</span><span class="sxs-lookup"><span data-stu-id="3b257-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3b257-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3b257-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3b257-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="3b257-112">Remarks</span></span>

<span data-ttu-id="3b257-113">Jako neutrální v této operaci se volá `M(q)` hned po `SetToBasisState(result, q)` návratu `result` .</span><span class="sxs-lookup"><span data-stu-id="3b257-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>