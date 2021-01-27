---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Uživatelem definovaný typ ControlledRotation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847398"
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

## <a name="example"></a>Příklad

Následující představuje rotaci o $X $ osa prvního qubit v registru, řízená na druhé qubit a s úhlem daným čtvrtým parametrem sekvenčního modelu:

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a>Poznámky

Neřízené otočení lze reprezentovat nastavením `ControlIndices` na prázdné pole indexů `new Int[0]` .