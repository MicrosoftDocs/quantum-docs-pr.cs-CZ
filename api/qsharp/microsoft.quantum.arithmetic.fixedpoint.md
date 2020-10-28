---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: Uživatelem definovaný typ FixedPoint
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: f1370cd2f8a7d6488ae0f6be841abd95e61f038e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707296"
---
# <a name="fixedpoint-user-defined-type"></a>Uživatelem definovaný typ FixedPoint

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


Představuje registr qubits čísla s pevnou desetinnou čárkou. Se skládá z celého čísla, které se rovná počtu qubits vlevo od binárního bodu, tj. qubits váhy větší než nebo rovno 1 a registr.

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

