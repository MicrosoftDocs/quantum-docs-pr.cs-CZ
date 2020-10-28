---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: Operace AssertQubitWithinTolerance
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 3fe4aa739c5e15199401aecb76ef551e52f6dcff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698125"
---
# <a name="assertqubitwithintolerance-operation"></a>Operace AssertQubitWithinTolerance

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček [](https://nuget.org/packages/)


Vyhodnotí, že qubit `q` je v očekávané eigenstate operátoru Pauli z až po danou toleranci.

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>Vstup

### <a name="expected--__invalidresult__"></a>očekáváno __: <Result> neplatné__

Který stav qubit má být v: `Zero` nebo `One` .


### <a name="q--qubit"></a>Otázka: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, jehož stav je uplatněn.


### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerance u pravděpodobnosti měření qubit vracející očekávaný výsledek.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> Umožňuje vyhodnotit libovolný stav qubit spíše než jenom $Z $ eigenstates.

## <a name="see-also"></a>Viz také

- [Microsoft. AssertQubitIsInStateWithinTolerance. Diagnostics.](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)