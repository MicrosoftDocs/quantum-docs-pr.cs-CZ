---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Uživatelem definovaný typ UnivariateOptimizationResult
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708788"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>Uživatelem definovaný typ UnivariateOptimizationResult

Obor názvů: [Microsoft.. Optimization](xref:Microsoft.Quantum.Optimization)

Balíček [](https://nuget.org/packages/)


Představuje výsledek optimalizace funkce univariate.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Pojmenované položky

### <a name="coordinate--double"></a>Souřadnice: [Double](xref:microsoft.quantum.lang-ref.double)

Vstup, při kterém byl nalezen optimální čas
### <a name="value--double"></a>Hodnota: [Double](xref:microsoft.quantum.lang-ref.double)

Hodnota vrácená funkcí na optimálním místě.