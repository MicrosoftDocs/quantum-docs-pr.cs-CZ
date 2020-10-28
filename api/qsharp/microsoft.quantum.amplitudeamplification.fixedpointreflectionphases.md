---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 6ab2a8c6cb0b390f96aa13ece5d5b89c196a6107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707732"
---
# <a name="fixedpointreflectionphases-function"></a>FixedPointReflectionPhases – funkce

Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)

Balíček [](https://nuget.org/packages/)


Vypočítá částečné odrazové fáze pro zesílení amplitudy s pevnou desetinnou čárkou.

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Vstup

### <a name="nqueries--int"></a>nQueries: [int](xref:microsoft.quantum.lang-ref.int)

Počet dotazů na přípravu stavu Oracle. Musí být liché celé číslo.


### <a name="successmin--double"></a>successMin: [Double](xref:microsoft.quantum.lang-ref.double)

Cíl minimální pravděpodobnosti úspěšnosti.



## <a name="output--reflectionphases"></a>Výstup: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Pole fází, které lze použít při implementaci algoritmu amplitudy amplitudy s pevnou desetinnou čárkou.

## <a name="references"></a>Odkazy

Použijeme fáze v zesílení amplitudy s pevnou desetinnou čárkou s optimálním počtem dotazů.

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Viz také "metodologie kompozitních" bran pro plnění "
- [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) pro fáze ve `RotationPhases` formátu.