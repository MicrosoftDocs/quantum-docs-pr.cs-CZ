---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: c2d094a6d0e0c7cecb249cd517995e11dff3d3b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854611"
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