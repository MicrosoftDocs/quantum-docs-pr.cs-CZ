---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Operace MaybeChooseElement
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 86a69110fc92a2b6238cc757c09185c9fbcdb035
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856111"
---
# <a name="maybechooseelement-operation"></a>Operace MaybeChooseElement

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


V případě pole dat a distribuce v rámci indexů se pokusí zvolit element náhodně.

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a>Vstup

### <a name="data--t"></a>data: t []

Pole, ze kterého se má vybrat element


### <a name="indexdistribution--discretedistribution"></a>indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Rozdělení na indexy `data` .



## <a name="output--boolt"></a>Výstup: ([bool](xref:microsoft.quantum.lang-ref.bool), t)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="example"></a>Příklad

Následující fragment Q # vybírá element náhodně z pole:

```qsharp
let (succeeded, element) = MaybeChooseElement(
    data,
    DiscreteUniformDistribution(0, Length(data) - 1)
);
Fact(succeeded, "Index chosen by MaybeChooseElement was not valid.");
```