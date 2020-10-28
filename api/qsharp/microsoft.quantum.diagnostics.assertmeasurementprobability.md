---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: Operace AssertMeasurementProbability
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: ff0419706d825442492f82e564f1cce86f1b112f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698153"
---
# <a name="assertmeasurementprobability-operation"></a>Operace AssertMeasurementProbability

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček [](https://nuget.org/packages/)


Vyhodnotí, že měření daného qubits v daném Pauli základu bude mít daný výsledek s danou pravděpodobností v rámci určité tolerance.

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit
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