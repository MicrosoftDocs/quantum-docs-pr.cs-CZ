---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Uživatelem definovaný typ ControlledRotation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: afc425c16ab550fd414e656484c9ff6f0f8f3ef4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697692"
---
# <a name="controlledrotation-user-defined-type"></a>Uživatelem definovaný typ ControlledRotation

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček [](https://nuget.org/packages/)


Popisuje řízené otočení z pohledu na své cílové a řídicí indexy, osu natočení a index do vektoru parametru modelu.

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a>Pojmenované položky

### <a name="targetindex--int"></a>TargetIndex: [int](xref:microsoft.quantum.lang-ref.int)

Index cílového qubit pro toto řízené otočení.
### <a name="controlindices--int"></a>ControlIndices: [int](xref:microsoft.quantum.lang-ref.int)[]

Pole qubity ovládacího prvku pro toto otočení.
### <a name="axis--pauli"></a>Osa: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Osa pro toto otočení
### <a name="parameterindex--int"></a>ParameterIndex: [int](xref:microsoft.quantum.lang-ref.int)

Index na vektor parametru modelu popisující úhel pro toto otočení.

## <a name="remarks"></a>Poznámky

Neřízené otočení lze reprezentovat nastavením `ControlIndices` na prázdné pole indexů `new Int[0]` .