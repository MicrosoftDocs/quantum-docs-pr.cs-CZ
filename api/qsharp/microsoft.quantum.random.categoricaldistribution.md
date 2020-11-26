---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 2e3d9b17939d5a9a5bc5e7d89a843e0ff5a848ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210246"
---
# <a name="categoricaldistribution-function"></a>CategoricalDistribution – funkce

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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