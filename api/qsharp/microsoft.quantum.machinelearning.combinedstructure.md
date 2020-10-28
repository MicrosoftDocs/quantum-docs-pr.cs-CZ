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
# <a name="combinedstructure-function"></a><span data-ttu-id="4722e-102">CombinedStructure – funkce</span><span class="sxs-lookup"><span data-stu-id="4722e-102">CombinedStructure function</span></span>

<span data-ttu-id="4722e-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4722e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="4722e-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4722e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4722e-105">Vzhledem k jedné nebo více vrstvám řízených otočení vrátí jednu vrstvu s indexem parametru, který je posunut tak, aby jednotlivé vrstvy byly parametrizované pomocí různých parametrů modelu.</span><span class="sxs-lookup"><span data-stu-id="4722e-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="4722e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4722e-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="4722e-107">vrstvy: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="4722e-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="4722e-108">Vrstvy, které mají být kombinovány.</span><span class="sxs-lookup"><span data-stu-id="4722e-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="4722e-109">Výstup: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="4722e-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="4722e-110">Jedna vrstva řízených otočení, která představuje zřetězení všech ostatních vrstev.</span><span class="sxs-lookup"><span data-stu-id="4722e-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>