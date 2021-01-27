---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: Uživatelem definovaný typ FixedPoint
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 18e85120647c5a1f41ccab5fbfb27ea602a279af
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843205"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="e61ed-102">Uživatelem definovaný typ FixedPoint</span><span class="sxs-lookup"><span data-stu-id="e61ed-102">FixedPoint user defined type</span></span>

<span data-ttu-id="e61ed-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e61ed-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e61ed-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="e61ed-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="e61ed-105">Představuje registr qubits čísla s pevnou desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="e61ed-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="e61ed-106">Se skládá z celého čísla, které se rovná počtu qubits vlevo od binárního bodu, tj. qubits váhy větší než nebo rovno 1 a registr.</span><span class="sxs-lookup"><span data-stu-id="e61ed-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

