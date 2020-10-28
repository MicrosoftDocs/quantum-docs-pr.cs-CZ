---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705809"
---
# <a name="rectangulararrayfact-function"></a>RectangularArrayFact – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


Představuje podmínku, že dvourozměrné pole má obdélníkový tvar.

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>Popis

Tato funkce vyhodnotí, že každý řádek v poli má stejnou délku.

## <a name="input"></a>Vstup

### <a name="array--t"></a>Array: t [] []

Dvojrozměrné pole prvků


### <a name="message--string"></a>zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)

Zpráva, která se má vytisknout, pokud pole není obdélníkové pole



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ každého prvku `array` .

## <a name="see-also"></a>Viz také

- [Microsoft. Forms. Arrays. SquareArrayFact](xref:Microsoft.Quantum.Arrays.SquareArrayFact)