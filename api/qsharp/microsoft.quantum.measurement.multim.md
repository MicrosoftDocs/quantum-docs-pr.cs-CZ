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
# <a name="multim-operation"></a>Operace MultiM

Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Měří jednotlivé qubity v daném poli na úrovni Standard.

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a>Vstup

### <a name="targets--qubit"></a>cíle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Pole qubits, které se má změřit



## <a name="output--__invalidresult__"></a>Výstup: __neplatný <Result>__[]

Pole výsledků měření.