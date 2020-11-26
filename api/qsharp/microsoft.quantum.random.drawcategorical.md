---
uid: Microsoft.Quantum.Random.DrawCategorical
title: Operace DrawCategorical
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a5826aa5f658fea766db0ca5ccbb9c0d7d056d4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192991"
---
# <a name="drawcategorical-operation"></a>Operace DrawCategorical

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Nakreslí náhodný vzorek z kategorií distribuce určené seznamem probablities.

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a>Popis

Pravděpodobnost výběru konkrétního indexu je úměrná hodnotě prvku pole v daném indexu.
Prvky pole, které jsou rovny nule, se ignorují a jejich indexy se nikdy nevrátí. Pokud je některý prvek pole menší než nula, nebo pokud žádný element pole není větší než nula, operace se nezdařila.

## <a name="input"></a>Vstup

### <a name="probs--double"></a>sondy: [Double](xref:microsoft.quantum.lang-ref.double)[]

Pole čísel s plovoucí desetinnou čárkou, které je úměrné pravděpodobnosti výběru každého indexu.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Celé číslo $i $ s pravděpodobností $ \Pr (i) = p_i/\ sum_i p_i $, kde $p _i $ je prvek $i $ th `probs` .

## <a name="see-also"></a>Viz také

- [Microsoft. prohodilá. CategoricalDistribution](xref:Microsoft.Quantum.Random.CategoricalDistribution)