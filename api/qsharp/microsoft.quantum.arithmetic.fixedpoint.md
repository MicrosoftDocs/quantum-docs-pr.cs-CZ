---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: Uživatelem definovaný typ FixedPoint
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 0fea6e4ee1b8c5391e815217f1ddf9e511d46463
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223098"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="16f09-102">Uživatelem definovaný typ FixedPoint</span><span class="sxs-lookup"><span data-stu-id="16f09-102">FixedPoint user defined type</span></span>

<span data-ttu-id="16f09-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="16f09-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="16f09-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="16f09-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="16f09-105">Představuje registr qubits čísla s pevnou desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="16f09-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="16f09-106">Se skládá z celého čísla, které se rovná počtu qubits vlevo od binárního bodu, tj. qubits váhy větší než nebo rovno 1 a registr.</span><span class="sxs-lookup"><span data-stu-id="16f09-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

