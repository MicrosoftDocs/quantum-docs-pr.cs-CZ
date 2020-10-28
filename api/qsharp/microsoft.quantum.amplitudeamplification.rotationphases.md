---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Uživatelem definovaný typ RotationPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707695"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="15bd6-102">Uživatelem definovaný typ RotationPhases</span><span class="sxs-lookup"><span data-stu-id="15bd6-102">RotationPhases user defined type</span></span>

<span data-ttu-id="15bd6-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="15bd6-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="15bd6-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="15bd6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="15bd6-105">Fáze pro sekvenci qubit otočení v zesílení amplitudy.</span><span class="sxs-lookup"><span data-stu-id="15bd6-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="15bd6-106">Poznámky</span><span class="sxs-lookup"><span data-stu-id="15bd6-106">Remarks</span></span>

<span data-ttu-id="15bd6-107">První parametr je pole fází pro odrazy vyjádřené jako součin qubit otočení.</span><span class="sxs-lookup"><span data-stu-id="15bd6-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="15bd6-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="15bd6-108">[ G.H.</span></span> <span data-ttu-id="15bd6-109">Nízká, I. L.</span><span class="sxs-lookup"><span data-stu-id="15bd6-109">Low, I. L.</span></span> <span data-ttu-id="15bd6-110">Čuangština, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="15bd6-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>