---
uid: Microsoft.Quantum.Measurement.MultiM
title: Operace MultiM
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: c39601f3e8b272b9341f1789b4c8e7230cb4182c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226991"
---
# <a name="multim-operation"></a><span data-ttu-id="e9fb5-102">Operace MultiM</span><span class="sxs-lookup"><span data-stu-id="e9fb5-102">MultiM operation</span></span>

<span data-ttu-id="e9fb5-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="e9fb5-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="e9fb5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e9fb5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e9fb5-105">Měří jednotlivé qubity v daném poli na úrovni Standard.</span><span class="sxs-lookup"><span data-stu-id="e9fb5-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="e9fb5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e9fb5-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="e9fb5-107">cíle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e9fb5-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e9fb5-108">Pole qubits, které se má změřit</span><span class="sxs-lookup"><span data-stu-id="e9fb5-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="e9fb5-109">Výstup: __neplatný <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="e9fb5-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="e9fb5-110">Pole výsledků měření.</span><span class="sxs-lookup"><span data-stu-id="e9fb5-110">An array of measurement results.</span></span>