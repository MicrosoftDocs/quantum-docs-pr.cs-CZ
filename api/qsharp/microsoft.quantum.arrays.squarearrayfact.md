---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: 3529718f0c903266d21fd593c11c0149dae0fa2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220191"
---
# <a name="squarearrayfact-function"></a>SquareArrayFact – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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