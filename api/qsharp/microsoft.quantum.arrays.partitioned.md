---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Dělená funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: 43d99a0e33a813e4af23a3890ace808e91c1049c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845547"
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



## <a name="example"></a>Příklad

```qsharp
// The following returns [[1, 5], [3], [7]];
let split = Partitioned([2,1], [1,5,3,7]);
```