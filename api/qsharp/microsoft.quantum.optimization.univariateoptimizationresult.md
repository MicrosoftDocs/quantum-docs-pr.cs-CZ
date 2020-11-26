---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Uživatelem definovaný typ UnivariateOptimizationResult
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194028"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>Uživatelem definovaný typ UnivariateOptimizationResult

Obor názvů: [Microsoft.. Optimization](xref:Microsoft.Quantum.Optimization)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje výsledek optimalizace funkce univariate.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Pojmenované položky

### <a name="coordinate--double"></a>Souřadnice: [Double](xref:microsoft.quantum.lang-ref.double)

Vstup, při kterém byl nalezen optimální čas
### <a name="value--double"></a>Hodnota: [Double](xref:microsoft.quantum.lang-ref.double)

Hodnota vrácená funkcí na optimálním místě.