---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Operace AssertPhase
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830080"
---
# <a name="assertphase-operation"></a>Operace AssertPhase

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vyhodnotí, že fáze rovného stavu pozice má očekávanou hodnotu.

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a>Popis

Tato operace vyhodnotí, že fáze $ \phi $ pro stav, který může být vyjádřen jako $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ KET {0} + e ^ {-i\phi} \ KET {1} ) $ pro některé reálné $t $ má očekávanou hodnotu.

## <a name="input"></a>Vstup

### <a name="expected--double"></a>očekáváno: [Double](xref:microsoft.quantum.lang-ref.double)

Očekávaná hodnota $ \phi \in (-\pi, \pi] $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, ve kterém je uložen očekávaný stav.


### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

Absolutní tolerance rozdílu mezi skutečnými a očekávanými hodnotami.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Příklad

Následující vyhodnocení je úspěšné: `qubit` je ve stavu $ \ket{\psi} = e ^ {i 0,5} \ sqrt {1/2} \ KET {0} + e ^ {i 0.5} \ sqrt {1/2} \ KET {1} $;

- `AssertPhase(0.0,qubit,10e-10);`

`qubit` je ve stavu $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ KET {0} + e ^ {-i 0,5} \ sqrt {1/2} \ KET {1} $;

- `AssertPhase(0.5,qubit,10e-10);`

`qubit` je ve stavu $ \ket{\psi} = e ^ {-i 2,2} \ sqrt {1/2} \ KET {0} + e ^ {i 0,2} \ sqrt {1/2} \ KET {1} $;

- `AssertPhase(-1.2,qubit,10e-10);`