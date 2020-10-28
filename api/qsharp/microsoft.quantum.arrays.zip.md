---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 32fea60fc36bfdbaa2ab2f3560f291bf4ce4fa51
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705681"
---
# <a name="zip-function"></a>Zip – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


> [!WARNING]
> Zip je zastaralý. <xref:Microsoft.Quantum.Arrays.Zipped>Místo toho ho použijte.

Zadaná dvě pole, vrátí nové pole párů tak, aby každá dvojice obsahovala element z každého původního pole.

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a>Vstup

### <a name="left--t"></a>Left: t []

Pole obsahující hodnoty pro první prvek řazené kolekce členů.


### <a name="right--u"></a>Right: ' U []

Pole obsahující hodnoty pro druhý prvek každé řazené kolekce členů.



## <a name="output--tu"></a>Výstup: (ne, ' U) []

Pole obsahující páry formuláře `(left[idx], right[idx])` pro každý `idx` . Pokud tato dvě pole nemají stejnou délku, výstup bude až na kratší dobu.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ levého prvku pole.
### <a name="u"></a>U

Typ pravého pole prvků.

## <a name="see-also"></a>Viz také

- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)
- [Microsoft. Forms. Arrays. Unzip](xref:Microsoft.Quantum.Arrays.Unzipped)