---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Operace AssertProbInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707440"
---
# <a name="assertprobint-operation"></a>Operace AssertProbInt

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


Vyhodnotí, že pravděpodobnost konkrétního stavu registru pro nepodmíněných hodnot má očekávanou hodnotu.

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a>Popis

Je-li zadána hodnota $n $-qubit se stavem $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, vyhodnotí, že pravděpodobnost $ | \ alpha_j | ^ 2 $ stavu $ \ket{j} $ indexovaného $j $ má očekávanou hodnotu.

## <a name="input"></a>Vstup

### <a name="stateindex--int"></a>stateIndex: [int](xref:microsoft.quantum.lang-ref.int)

Index $j $ stavu $ \ket{j} $ reprezentovaný `LittleEndian` registrem.


### <a name="expected--double"></a>očekáváno: [Double](xref:microsoft.quantum.lang-ref.double)

Očekávaná hodnota $ | \ alpha_j | ^ 2 $.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registr qubit ukládá \ket{\psi} $ ve formátu Little endian.


### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

Absolutní tolerance rozdílu mezi skutečnými a očekávanými hodnotami.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

