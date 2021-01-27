---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5d0af0a60217b69dc7eb8ece8952f2a7f0c09280
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847385"
---
# <a name="cyclicentanglinglayer-function"></a>CyclicEntanglingLayer – funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vrátí pole jednotlivě řízených otočení podél dané osy uspořádané cyklicky v rámci registru qubits a parametrizované pomocí různých parametrů modelu.

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Vstup

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits, které se v dané vrstvě jednalo.


### <a name="axis--pauli"></a>osa: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Osa otočení pro každé otočení v dané vrstvě


### <a name="stride--int"></a>Rozteč: [int](xref:microsoft.quantum.lang-ref.int)

Oddělení mezi cílovou a řídicí index pro každé otočení.



## <a name="output--controlledrotation"></a>Výstup: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Pole qubit řízených otočení, která jsou rozložená cyklicky v rámci registru `nQubits` qubits.

## <a name="example"></a>Příklad

Následují ekvivalenty:

```qsharp
let layer = CyclicEntanglingLayer(3, PauliX, 2);
let layer = [
    ControlledRotation((0, [2]), PauliX, 0),
    ControlledRotation((1, [0]), PauliX, 1),
    ControlledRotation((2, [1]), PauliX, 2)
];
```