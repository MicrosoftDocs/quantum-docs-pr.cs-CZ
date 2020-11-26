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
# <a name="rotationphases-user-defined-type"></a>Uživatelem definovaný typ RotationPhases

Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fáze pro sekvenci qubit otočení v zesílení amplitudy.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Poznámky

První parametr je pole fází pro odrazy vyjádřené jako součin qubit otočení.
[ G.H. Nízká, I. L. Čuangština, https://arxiv.org/abs/1707.05391 ].