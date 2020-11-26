---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Operace EstimateTermExpectation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 3f0ff5037b1424abb6fb318bd49ffd89f545822d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224645"
---
# <a name="estimatetermexpectation-operation"></a>Operace EstimateTermExpectation

Obor názvů: [Microsoft. JordanWigner. chemie.. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Vypočítá spotřebu energie spojenou s daným Jordan-Wigner Hamiltonian období

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>Popis

Tato operace odhadne očekávanou hodnotu přidruženou ke každému operátoru měření a vynásobí ji odpovídajícím koeficientem pomocí vzorkování.
Výsledky jsou shrnuty do proměnné, která obsahuje energii Jordan-Wignerho termínu.

## <a name="input"></a>Vstup

### <a name="inputstateunitary--qubit--unit--is-adj"></a>inputStateUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Jednotná použití pro přípravu stavu.


### <a name="ops--pauli"></a>Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Měřicí operátory Jordan-Wignerho termínu.


### <a name="coeffs--double"></a>coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]

Koeficienty Jordan-Wignerho termínu.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits potřebných pro simulaci molekulárního systému.


### <a name="nsamples--int"></a>nSamples: [int](xref:microsoft.quantum.lang-ref.int)

Počet vzorků, které se mají použít pro odhad očekávaného termínu.



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)

Energie přidružená k Jordan-Wignermu období.