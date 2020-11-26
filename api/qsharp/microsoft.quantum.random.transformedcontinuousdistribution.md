---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: b317eaaa0ff0180ea5d240464c96d1c6b59c9c70
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226260"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution – funkce

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


S ohledem na průběžnou distribuci vrátí novou distribuci, která transformuje originál pomocí dané funkce.

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Vstup

### <a name="transform--double---double"></a>Transform: [Dvojitá](xref:microsoft.quantum.lang-ref.double) -> [Dvojitá přesnost](xref:microsoft.quantum.lang-ref.double)

Funkce, která transformuje variates původního rozdělení do transformované distribuce.


### <a name="distribution--continuousdistribution"></a>distribuce: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Původní distribuce, která se má transformovat.



## <a name="output--continuousdistribution"></a>Výstup: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Nové rozdělení související s transformací, kterou `distribution` předává `transform` .