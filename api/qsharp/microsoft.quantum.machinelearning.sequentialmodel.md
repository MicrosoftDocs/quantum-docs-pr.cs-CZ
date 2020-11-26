---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Uživatelem definovaný typ SequentialModel
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: 3afdb8dafe0179535fe5d8c3dff668f1f3de2f7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196170"
---
# <a name="sequentialmodel-user-defined-type"></a>Uživatelem definovaný typ SequentialModel

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Popisuje model třídění podle počtu stavů složený z sekvence parametrizovaných a řízených otočení, přiřazení úhlů otočení a posunutí mezi dvěma třídami rozpoznávanými modelem.

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a>Pojmenované položky

### <a name="structure--controlledrotation"></a>Struktura: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Sekvence řízených otočení používaných ke klasifikaci vstupů.
### <a name="parameters--double"></a>Parametry: [Double](xref:microsoft.quantum.lang-ref.double)[]

Přiřazení úhlů otočení k dané struktuře klasifikace.
### <a name="bias--double"></a>Bias: [Double](xref:microsoft.quantum.lang-ref.double)

Posun mezi dvěma třídami rozpoznávanými tímto tříděním.

## <a name="references"></a>Reference

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)