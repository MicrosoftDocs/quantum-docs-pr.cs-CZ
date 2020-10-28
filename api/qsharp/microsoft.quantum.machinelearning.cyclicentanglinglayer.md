---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 6e0f5057b35baefe2677126ba70ee4fddde7d4db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706872"
---
# <a name="cyclicentanglinglayer-function"></a>CyclicEntanglingLayer – funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček [](https://nuget.org/packages/)


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