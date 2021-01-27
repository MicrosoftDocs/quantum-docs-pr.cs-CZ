---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 5d50b3fdc2b0f948e93cb11b5c69403d97574ccd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843943"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="76f79-102">RotationPhasesAsReflectionPhases – funkce</span><span class="sxs-lookup"><span data-stu-id="76f79-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="76f79-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="76f79-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="76f79-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76f79-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76f79-105">Převede fáze zadané jako qubit otočení na fáze určené jako částečné odrazy.</span><span class="sxs-lookup"><span data-stu-id="76f79-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="76f79-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="76f79-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="76f79-107">rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="76f79-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="76f79-108">Pole rotací s jednou qubit, která se mají převést na částečné odrazy</span><span class="sxs-lookup"><span data-stu-id="76f79-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="76f79-109">Výstup: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="76f79-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="76f79-110">Operace, která implementuje fáze určené jako částečné odrazy.</span><span class="sxs-lookup"><span data-stu-id="76f79-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="76f79-111">Reference</span><span class="sxs-lookup"><span data-stu-id="76f79-111">References</span></span>

<span data-ttu-id="76f79-112">Konvence používáme v</span><span class="sxs-lookup"><span data-stu-id="76f79-112">We use the convention in</span></span>

- <span data-ttu-id="76f79-113">[ *G.H. nízká, I. L. Čuangština*](https://arxiv.org/abs/1707.05391) pro související fáze rotace s jedním qubit pro fáze operátoru reflexe.</span><span class="sxs-lookup"><span data-stu-id="76f79-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>