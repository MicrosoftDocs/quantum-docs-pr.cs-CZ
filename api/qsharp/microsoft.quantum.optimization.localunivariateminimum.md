---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: e804e6a6ed82f14dcc9b8f721ad503d77922dc0f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194079"
---
# <a name="localunivariateminimum-function"></a>LocalUnivariateMinimum – funkce

Obor názvů: [Microsoft.. Optimization](xref:Microsoft.Quantum.Optimization)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí místní minimum pro funkci univariate v rámci ohraničeného intervalu pomocí hledání zlatého intervalu.

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a>Vstup

### <a name="fn--double---double"></a>FN: [Dvojitá](xref:microsoft.quantum.lang-ref.double) -> [Dvojitá přesnost](xref:microsoft.quantum.lang-ref.double)

Funkce univariate, která se má minimalizovat


### <a name="bounds--doubledouble"></a>meze: ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))

Interval, ve kterém má být nalezeno místní minimum.


### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

Je možné, že se má tolerovat přesnost vstupu na funkci.
Hledání místních Optima bude pokračovat, dokud se interval nezmenší na šířku, než je tato tolerance.



## <a name="output--univariateoptimizationresult"></a>Výstup: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)

Místní Optima dané funkce, umístěný v rámci daných hranic.