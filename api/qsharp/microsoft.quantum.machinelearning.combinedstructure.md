---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: fbfd87761a40abe350e5f955fb53d8024eeb614e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706873"
---
# <a name="combinedstructure-function"></a>CombinedStructure – funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček [](https://nuget.org/packages/)


Vzhledem k jedné nebo více vrstvám řízených otočení vrátí jednu vrstvu s indexem parametru, který je posunut tak, aby jednotlivé vrstvy byly parametrizované pomocí různých parametrů modelu.

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Vstup

### <a name="layers--controlledrotation"></a>vrstvy: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []

Vrstvy, které mají být kombinovány.



## <a name="output--controlledrotation"></a>Výstup: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Jedna vrstva řízených otočení, která představuje zřetězení všech ostatních vrstev.