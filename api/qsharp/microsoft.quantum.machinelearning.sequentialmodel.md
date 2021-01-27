---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Uživatelem definovaný typ SequentialModel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: ab9c121884e489b5d056285008c91c1ad70bb053
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854892"
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