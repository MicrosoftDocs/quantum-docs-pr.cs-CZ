---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: 3b09af88bbed20a392768d005e5e9567b3bb7022
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697593"
---
# <a name="localunivariateminimum-function"></a>LocalUnivariateMinimum – funkce

Obor názvů: [Microsoft.. Optimization](xref:Microsoft.Quantum.Optimization)

Balíček [](https://nuget.org/packages/)


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