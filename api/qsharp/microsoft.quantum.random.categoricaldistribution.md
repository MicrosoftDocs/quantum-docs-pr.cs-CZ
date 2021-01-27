---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842348"
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

## <a name="example"></a>Příklad

Následující kód Q # bude zobrazovat 0 s pravděpodobností 30% a 1 s pravděpodobností 70%:

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```