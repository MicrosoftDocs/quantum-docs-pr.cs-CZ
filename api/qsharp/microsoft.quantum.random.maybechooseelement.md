---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Operace MaybeChooseElement
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 1a69c8d5a6ae022ceda9269e17434b740809b107
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192855"
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

