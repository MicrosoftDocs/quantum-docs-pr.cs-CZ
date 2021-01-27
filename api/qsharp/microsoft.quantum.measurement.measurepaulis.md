---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: Operace MeasurePaulis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 1bc14ec8e7c608d1195a03a354c71e870594f86d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853772"
---
# <a name="measurepaulis-operation"></a>Operace MeasurePaulis

Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


V případě pole qubitch operátorů Pauli, měří jednotlivé míry pomocí určené míry měření a vrátí pole výsledků.

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a>Vstup

### <a name="paulis--pauli"></a>Pauls: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Pole qubitch Paulich operátorů k měření.


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Zaregistrujte, na které se mají měřit dané operátory.


### <a name="gadget--pauliqubit--__invalidresult__"></a>gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __neplatné <Result>__ 

Operace, která provádí měření daného qubit operátoru.



## <a name="output--__invalidresult__"></a>Výstup: __neplatný <Result>__[]

Pole výsledků získané z měření každého elementu `paulis` v `target` .