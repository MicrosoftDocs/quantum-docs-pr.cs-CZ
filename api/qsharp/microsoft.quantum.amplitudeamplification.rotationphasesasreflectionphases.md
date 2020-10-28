---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: d62a7584324c9467ccc759e4bed81acbceee719c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707689"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="3cc37-102">RotationPhasesAsReflectionPhases – funkce</span><span class="sxs-lookup"><span data-stu-id="3cc37-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="3cc37-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="3cc37-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="3cc37-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3cc37-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3cc37-105">Převede fáze zadané jako qubit otočení na fáze určené jako částečné odrazy.</span><span class="sxs-lookup"><span data-stu-id="3cc37-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="3cc37-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3cc37-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="3cc37-107">rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="3cc37-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="3cc37-108">Pole rotací s jednou qubit, která se mají převést na částečné odrazy</span><span class="sxs-lookup"><span data-stu-id="3cc37-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="3cc37-109">Výstup: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="3cc37-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="3cc37-110">Operace, která implementuje fáze určené jako částečné odrazy.</span><span class="sxs-lookup"><span data-stu-id="3cc37-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="3cc37-111">Odkazy</span><span class="sxs-lookup"><span data-stu-id="3cc37-111">References</span></span>

<span data-ttu-id="3cc37-112">Konvence používáme v</span><span class="sxs-lookup"><span data-stu-id="3cc37-112">We use the convention in</span></span>

- <span data-ttu-id="3cc37-113">[ *G.H. nízká, I. L. Čuangština*](https://arxiv.org/abs/1707.05391) pro související fáze rotace s jedním qubit pro fáze operátoru reflexe.</span><span class="sxs-lookup"><span data-stu-id="3cc37-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>