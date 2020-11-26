---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Uživatelem definovaný typ ControlledRotation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 1e664b470caeba656ea4a73f70bbc0ef5fe76f7e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196561"
---
# <a name="controlledrotation-user-defined-type"></a>Uživatelem definovaný typ ControlledRotation

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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