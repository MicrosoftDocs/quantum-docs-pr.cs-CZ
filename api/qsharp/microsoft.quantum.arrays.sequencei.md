---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Sequence – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705793"
---
# <a name="sequencei-function"></a>Sequence – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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