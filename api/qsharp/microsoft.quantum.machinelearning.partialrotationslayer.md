---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: e230df9b28c59e1d532d5b36adf90efa01f0f33e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852920"
---
# <a name="partialrotationslayer-function"></a>PartialRotationsLayer – funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vrátí pole rotací s jednou qubit podél dané osy, parametrizované pomocí různých parametrů modelu.

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Vstup

### <a name="idxsqubits--int"></a>idxsQubits: [int](xref:microsoft.quantum.lang-ref.int)[]

Indexy pro qubits, které se mají použít jako cíle pro každé otočení.


### <a name="axis--pauli"></a>osa: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Osa otočení pro každé otočení v dané vrstvě



## <a name="output--controlledrotation"></a>Výstup: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Pole řízených otočení o dané ose, jednu na každé `nQubits` qubits.