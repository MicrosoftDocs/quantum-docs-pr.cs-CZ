---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Operace AssertMeasurement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698169"
---
# <a name="assertmeasurement-operation"></a>Operace AssertMeasurement

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček [](https://nuget.org/packages/)


Vyhodnotí, že měření daného qubits v dané Pauli základu bude mít vždy daný výsledek.

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
```


## <a name="input"></a>Vstup

### <a name="bases--pauli"></a>základ: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Měřicí efekt pro vyhodnocení pravděpodobnosti vyjádřené jako qubit Pauli operátor.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr, na který se má kontrolní výraz provést.


### <a name="result--__invalidresult__"></a>výsledek: __neplatné <Result>__

Očekávaný výsledek `Measure(bases, qubits)` .


### <a name="msg--string"></a>Msg: [řetězec](xref:microsoft.quantum.lang-ref.string)

Zpráva, která má být hlášena v případě, že se kontrolní výraz nezdařil.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Všimněte si, že sousední a kontrolované verze této operace nekontrolují podmínku.

## <a name="see-also"></a>Viz také

- [Microsoft. AssertMeasurementProbability. Diagnostics.](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)