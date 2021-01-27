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
# <a name="fixedpoint-user-defined-type"></a>Uživatelem definovaný typ FixedPoint

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Představuje registr qubits čísla s pevnou desetinnou čárkou. Se skládá z celého čísla, které se rovná počtu qubits vlevo od binárního bodu, tj. qubits váhy větší než nebo rovno 1 a registr.

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

