---
uid: Microsoft.Quantum.Measurement.MultiM
title: Operace MultiM
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: b7f4083bde84c204611ea33746ae351a3e27b946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856998"
---
# <a name="multim-operation"></a><span data-ttu-id="8b3ef-102">Operace MultiM</span><span class="sxs-lookup"><span data-stu-id="8b3ef-102">MultiM operation</span></span>

<span data-ttu-id="8b3ef-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="8b3ef-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="8b3ef-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b3ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b3ef-105">Měří jednotlivé qubity v daném poli na úrovni Standard.</span><span class="sxs-lookup"><span data-stu-id="8b3ef-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="8b3ef-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8b3ef-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="8b3ef-107">cíle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8b3ef-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8b3ef-108">Pole qubits, které se má změřit</span><span class="sxs-lookup"><span data-stu-id="8b3ef-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="8b3ef-109">Výstup: __neplatný <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="8b3ef-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="8b3ef-110">Pole výsledků měření.</span><span class="sxs-lookup"><span data-stu-id="8b3ef-110">An array of measurement results.</span></span>