---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operace MeasureAllZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 6c44ab6a7983697644071f0e3cf106e9825661ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227076"
---
# <a name="measureallz-operation"></a>Operace MeasureAllZ

Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Společně měří Registry qubits v Pauli Z.

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>Popis

Měří Registry qubits v $Z \otimes Z \otimes \cdots \otimes Z $, které představují paritu celého registru.

## <a name="input"></a>Vstup

### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr, který se má měřit



## <a name="output--__invalidresult__"></a>Výstup: __neplatný <Result>__

Výsledek měření $Z \otimes Z \otimes \cdots \otimes Z $.