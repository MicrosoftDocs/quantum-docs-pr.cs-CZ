---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Operace AssertProbInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843407"
---
# <a name="assertprobint-operation"></a>Operace AssertProbInt

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Příklad

Předpokládejme, že `qubits` registr zakóduje qubit stav 3 \ket{\psi} = \ sqrt {1/8} \ KET {0} + \ sqrt {7/8} \ KET {6} $ ve formátu Little endian.
To znamená, že počet stavů $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ a $ \ket \equiv\ket \ket {6} {0} {1} \ket {1} $. Následující kontrolní výrazy jsou úspěšné:

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```