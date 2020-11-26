---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Uživatelem definovaný typ RotationPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 60fcda7d58a19f8891e252ddb18b504afddf5514
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191359"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="5201c-102">Uživatelem definovaný typ RotationPhases</span><span class="sxs-lookup"><span data-stu-id="5201c-102">RotationPhases user defined type</span></span>

<span data-ttu-id="5201c-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="5201c-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="5201c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5201c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5201c-105">Fáze pro sekvenci qubit otočení v zesílení amplitudy.</span><span class="sxs-lookup"><span data-stu-id="5201c-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="5201c-106">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5201c-106">Remarks</span></span>

<span data-ttu-id="5201c-107">První parametr je pole fází pro odrazy vyjádřené jako součin qubit otočení.</span><span class="sxs-lookup"><span data-stu-id="5201c-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="5201c-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="5201c-108">[ G.H.</span></span> <span data-ttu-id="5201c-109">Nízká, I. L.</span><span class="sxs-lookup"><span data-stu-id="5201c-109">Low, I. L.</span></span> <span data-ttu-id="5201c-110">Čuangština, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="5201c-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>