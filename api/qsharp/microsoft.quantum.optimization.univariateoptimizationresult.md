---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Uživatelem definovaný typ UnivariateOptimizationResult
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: cc54c0035796aac86482e8a3a6896ceb197c7cfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854569"
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