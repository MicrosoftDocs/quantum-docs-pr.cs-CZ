---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: 1549f24427f19bacbadf72e00c1c0181b64bcb73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211725"
---
# <a name="localrotationslayer-function"></a>LocalRotationsLayer – funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vrátí pole neřízených (jednoduchých-qubit) otočení podél dané osy s jedním otočením pro každý qubit v registru, které je parametrizované pomocí různých parametrů modelu.

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Vstup

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits, které se v dané vrstvě jednalo.


### <a name="axis--pauli"></a>osa: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Osa otočení pro každé otočení v dané vrstvě



## <a name="output--controlledrotation"></a>Výstup: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Pole řízených otočení o dané ose, jednu na každé `nQubits` qubits.