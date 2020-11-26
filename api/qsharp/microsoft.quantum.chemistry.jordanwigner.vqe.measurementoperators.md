---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: a5ea9a776f522e927f2f4545bd417d35bda83994
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214343"
---
# <a name="measurementoperators-function"></a>MeasurementOperators – funkce

Obor názvů: [Microsoft. JordanWigner. chemie.. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Vypočítá všechny operátory měření potřebné k výpočtu očekávaného Jordan-Wignerho termínu.

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a>Vstup

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits potřebných pro simulaci molekulárního systému.


### <a name="indices--int"></a>indexy: [int](xref:microsoft.quantum.lang-ref.int)[]

Pole obsahující indexy qubit každý operátor Pauli je aplikován na.


### <a name="termtype--int"></a>termType: [int](xref:microsoft.quantum.lang-ref.int)

Typ Jordan-Wigner podmínky.



## <a name="output--pauli"></a>Výstup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Pole operátorů měření (každý z nich je pole Pauli).