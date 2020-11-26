---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Dělená funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220497"
---
# <a name="partitioned-function"></a>Dělená funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rozdělí pole na více částí.

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Vstup

### <a name="nelements--int"></a>nElements: [int](xref:microsoft.quantum.lang-ref.int)[]

Počet prvků v každé části pole


### <a name="arr--t"></a>Šipka: t []

Vstupní pole, které se má rozdělit



## <a name="output--t"></a>Výstup: t [] []

Více polí, kde první pole je první `nElements[0]` z `arr` a druhé pole je další `nElements[1]` z `arr` atd. Poslední pole bude obsahovat všechny zbývající prvky.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

