---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: Operace MeasurePaulis
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 4faaf78f24fa28ae5e4f701b80d9297c910b975e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194215"
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