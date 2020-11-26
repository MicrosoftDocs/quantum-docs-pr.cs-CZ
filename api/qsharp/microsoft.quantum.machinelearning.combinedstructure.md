---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: 0a7d66be8b45d6a9df95b425e66b9b6bba241136
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211963"
---
# <a name="combinedstructure-function"></a>CombinedStructure – funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vzhledem k jedné nebo více vrstvám řízených otočení vrátí jednu vrstvu s indexem parametru, který je posunut tak, aby jednotlivé vrstvy byly parametrizované pomocí různých parametrů modelu.

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Vstup

### <a name="layers--controlledrotation"></a>vrstvy: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []

Vrstvy, které mají být kombinovány.



## <a name="output--controlledrotation"></a>Výstup: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Jedna vrstva řízených otočení, která představuje zřetězení všech ostatních vrstev.