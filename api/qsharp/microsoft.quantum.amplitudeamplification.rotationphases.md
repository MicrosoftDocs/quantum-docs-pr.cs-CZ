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
# <a name="rotationphases-user-defined-type"></a>Uživatelem definovaný typ RotationPhases

Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)

Balíček [](https://nuget.org/packages/)


Fáze pro sekvenci qubit otočení v zesílení amplitudy.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Poznámky

První parametr je pole fází pro odrazy vyjádřené jako součin qubit otočení.
[ G.H. Nízká, I. L. Čuangština, https://arxiv.org/abs/1707.05391 ].