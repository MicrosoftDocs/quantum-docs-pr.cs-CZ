---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: Operace AssertQubitWithinTolerance
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 7f57fc7a29d3eb86dc94cb24230d52b37eb6971d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853437"
---
# <a name="assertqubitwithintolerance-operation"></a>Operace AssertQubitWithinTolerance

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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