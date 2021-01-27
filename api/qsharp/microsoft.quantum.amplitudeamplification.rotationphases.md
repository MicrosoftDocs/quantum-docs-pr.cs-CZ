---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Uživatelem definovaný typ RotationPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843968"
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