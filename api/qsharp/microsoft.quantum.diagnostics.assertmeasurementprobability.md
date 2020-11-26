---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: Operace AssertMeasurementProbability
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 032b9224ad728f0637596668c2928a889deeba55
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202358"
---
# <a name="assertmeasurementprobability-operation"></a>Operace AssertMeasurementProbability

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vyhodnotí, že měření daného qubits v daném Pauli základu bude mít daný výsledek s danou pravděpodobností v rámci určité tolerance.

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="bases--pauli"></a>základ: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Měřicí efekt pro vyhodnocení pravděpodobnosti vyjádřené jako qubit Pauli operátor.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr, na který se má kontrolní výraz provést.


### <a name="result--__invalidresult__"></a>výsledek: __neplatné <Result>__

Očekávaný výsledek `Measure(bases, qubits)` .


### <a name="prob--double"></a>test: [Double](xref:microsoft.quantum.lang-ref.double)

Pravděpodobnost, se kterou se očekává daný výsledek.


### <a name="msg--string"></a>Msg: [řetězec](xref:microsoft.quantum.lang-ref.string)

Zpráva, která má být hlášena v případě, že se kontrolní výraz nezdařil.


### <a name="tol--double"></a>Typ platby: [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Všimněte si, že sousední a kontrolované verze této operace nekontrolují podmínku.

## <a name="see-also"></a>Viz také

- [Microsoft. AssertMeasurement. Diagnostics.](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)