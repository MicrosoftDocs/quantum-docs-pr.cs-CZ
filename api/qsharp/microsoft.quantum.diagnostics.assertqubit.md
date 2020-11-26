---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: Operace AssertQubit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 0e005230427bbd570133712679c51661e7ae6496
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202239"
---
# <a name="assertqubit-operation"></a>Operace AssertQubit

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vyhodnotí, že qubit `q` je v očekávané eigenstate operátoru Pauli z.

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a>Vstup

### <a name="expected--__invalidresult__"></a>očekáváno __: <Result> neplatné__

Který stav qubit má být v: `Zero` nebo `One` .


### <a name="q--qubit"></a>Otázka: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, jehož stav je uplatněn.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> Umožňuje vyhodnotit libovolný stav qubit spíše než jenom $Z $ eigenstates.

## <a name="see-also"></a>Viz také

- [Microsoft. AssertQubitIsInStateWithinTolerance. Diagnostics.](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)