---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: f7f0573db9098feebfd481624e11119c58fd9eed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705768"
---
# <a name="squarearrayfact-function"></a>SquareArrayFact – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


Představuje podmínku, že dvojrozměrné pole má čtvercový tvar.

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>Popis

Tato funkce vyhodnotí, že každý řádek v poli má tolik prvků, jako jsou řádky (elementy) v poli.

## <a name="input"></a>Vstup

### <a name="array--t"></a>Array: t [] []

Dvojrozměrné pole prvků


### <a name="message--string"></a>zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)

Zpráva, která se má vytisknout, pokud pole není čtvercové pole



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ každého prvku `array` .

## <a name="see-also"></a>Viz také

- [Microsoft. Forms. Arrays. RectangularArrayFact](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)