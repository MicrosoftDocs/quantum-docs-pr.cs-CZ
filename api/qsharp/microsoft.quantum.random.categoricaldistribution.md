---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708145"
---
# <a name="categoricaldistribution-function"></a>CategoricalDistribution – funkce

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček [](https://nuget.org/packages/)


Vrátí samostatnou distribuci kategorií, ve které je explicitně určena pravděpodobnost pro každý konečný seznam daných výsledků.

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Vstup

### <a name="probs--double"></a>sondy: [Double](xref:microsoft.quantum.lang-ref.double)[]

Pravděpodobnost pro každý výsledek kategorií rozdělení.
Tyto pravděpodobnosti nemusí být normalizovány, ale musí být všechny nezáporné.



## <a name="output--discretedistribution"></a>Výstup: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Index `i` s pravděpodobností `probs[i] / sum` , kde `sum` je součet `probs` vydaný pomocí `Fold(PlusD, 0.0, probs)` .