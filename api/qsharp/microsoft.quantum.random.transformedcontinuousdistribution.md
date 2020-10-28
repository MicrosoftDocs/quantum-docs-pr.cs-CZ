---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697572"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution – funkce

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček [](https://nuget.org/packages/)


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