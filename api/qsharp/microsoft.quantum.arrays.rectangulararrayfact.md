---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: b8ef7d52f7f815ca3e21ded1236e775a381646cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220412"
---
# <a name="rectangulararrayfact-function"></a>RectangularArrayFact – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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