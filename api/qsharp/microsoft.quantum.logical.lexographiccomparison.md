---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: de8179ab6e835d08e7f41287f31a876b7ecc91c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814386"
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