---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Dělená funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705848"
---
# <a name="partitioned-function"></a>Dělená funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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

