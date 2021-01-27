---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operace MeasureAllZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854676"
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