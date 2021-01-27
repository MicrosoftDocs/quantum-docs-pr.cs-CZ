---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 2ded197801111c26d8a33f9c2363b46ca4b6c4b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845848"
---
# <a name="fixedpointreflectionphases-function"></a>FixedPointReflectionPhases – funkce

Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="references"></a>Reference

Použijeme fáze v zesílení amplitudy s pevnou desetinnou čárkou s optimálním počtem dotazů.

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Viz také "metodologie kompozitních" bran pro plnění "
- [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) pro fáze ve `RotationPhases` formátu.