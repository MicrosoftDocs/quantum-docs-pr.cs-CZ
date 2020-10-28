---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operace MeasureAllZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697609"
---
# <a name="measureallz-operation"></a>Operace MeasureAllZ

Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)

Balíček [](https://nuget.org/packages/)


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