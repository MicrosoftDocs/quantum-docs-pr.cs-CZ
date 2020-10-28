---
uid: Microsoft.Quantum.Random.DrawCategorical
title: Operace DrawCategorical
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: fdc5ae3a9341cb11e8fda129bdd030289b6c99c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706720"
---
# <a name="drawcategorical-operation"></a>Operace DrawCategorical

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček [](https://nuget.org/packages/)


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