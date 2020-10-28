---
uid: Microsoft.Quantum.Measurement.MultiM
title: Operace MultiM
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: 36de9dbdfc96f6e1698ee4537405f7cb74e44262
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697600"
---
# <a name="multim-operation"></a><span data-ttu-id="abefb-102">Operace MultiM</span><span class="sxs-lookup"><span data-stu-id="abefb-102">MultiM operation</span></span>

<span data-ttu-id="abefb-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="abefb-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="abefb-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="abefb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="abefb-105">Měří jednotlivé qubity v daném poli na úrovni Standard.</span><span class="sxs-lookup"><span data-stu-id="abefb-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="abefb-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="abefb-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="abefb-107">cíle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="abefb-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="abefb-108">Pole qubits, které se má změřit</span><span class="sxs-lookup"><span data-stu-id="abefb-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="abefb-109">Výstup: __neplatný <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="abefb-109">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="abefb-110">Pole výsledků měření.</span><span class="sxs-lookup"><span data-stu-id="abefb-110">An array of measurement results.</span></span>