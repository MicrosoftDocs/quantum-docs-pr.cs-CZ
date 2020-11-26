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
# <a name="combinedstructure-function"></a><span data-ttu-id="2b771-102">CombinedStructure – funkce</span><span class="sxs-lookup"><span data-stu-id="2b771-102">CombinedStructure function</span></span>

<span data-ttu-id="2b771-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2b771-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2b771-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2b771-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="2b771-105">Vzhledem k jedné nebo více vrstvám řízených otočení vrátí jednu vrstvu s indexem parametru, který je posunut tak, aby jednotlivé vrstvy byly parametrizované pomocí různých parametrů modelu.</span><span class="sxs-lookup"><span data-stu-id="2b771-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="2b771-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2b771-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="2b771-107">vrstvy: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="2b771-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="2b771-108">Vrstvy, které mají být kombinovány.</span><span class="sxs-lookup"><span data-stu-id="2b771-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="2b771-109">Výstup: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="2b771-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="2b771-110">Jedna vrstva řízených otočení, která představuje zřetězení všech ostatních vrstev.</span><span class="sxs-lookup"><span data-stu-id="2b771-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>