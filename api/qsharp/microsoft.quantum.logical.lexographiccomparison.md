---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: 4d8596c52b0fc8082a2b766d95d4052a4964b8b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197580"
---
# <a name="lexographiccomparison-function"></a>LexographicComparison – funkce

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


S ohledem na funkci porovnání vrátí novou funkci, která lexographically porovnává dvě pole.

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a>Vstup

### <a name="elementcomparison--tt---bool"></a>elementComparison: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funkce, která porovná dva prvky `x` a `y` a vrátí, pokud `x` je menší nebo rovno `y` .



## <a name="output--tt---bool"></a>Výstup: (ne [], t [])-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funkce, která porovnává dvě pole `xs` a `ys` a vrátí, pokud se `xs` vyskytnou `ys` v pořadí lexographical nebo se rovná.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ prvků pole, které jsou porovnány.

## <a name="remarks"></a>Poznámky

Porovnání lexographic mezi dvěma poli `xs` a `ys` je definováno následujícím postupem. Říkáme, že dva prvky `x` a `y` jsou ekvivalentní, pokud `elementComparison(x, y)` a `elementComparison(y, x)` jsou obě true.

- Obě pole jsou porovnány elementem po prvku, dokud první dvojice prvků, které nejsou ekvivalentní. Pole obsahující prvek, který nastane jako první v závislosti na, `elementComparison` se říká, že se má objevit jako první v lexographical řazení.
- Pokud nejsou nalezeny žádné neekvivalentní prvky a jedno pole je delší než druhý, tak kratší pole se říká, že se má objevit jako první.

## <a name="see-also"></a>Viz také

- [Microsoft. Forms. Arrays. tříděné](xref:Microsoft.Quantum.Arrays.Sorted)