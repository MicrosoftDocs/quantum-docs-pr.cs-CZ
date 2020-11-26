---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Sequence – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220293"
---
# <a name="sequencei-function"></a>Sequence – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Získá pole celých čísel v daném intervalu.

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a>Vstup

### <a name="from--int"></a>od: [int](xref:microsoft.quantum.lang-ref.int)

Celkový počáteční index intervalu.


### <a name="to--int"></a>do: [int](xref:microsoft.quantum.lang-ref.int)

Celkový index v intervalu, který není menší než `from` .



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]

Pole obsahující sekvenci čísel `from` , `from + 1` ,..., `to` .