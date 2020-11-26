---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Sequence – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220259"
---
# <a name="sequencel-function"></a>Sequence – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Získá pole celých čísel v daném intervalu.

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a>Vstup

### <a name="from--bigint"></a>od: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Celkový počáteční index intervalu.


### <a name="to--bigint"></a>na: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Celkový index v intervalu, který není menší než `from` .



## <a name="output--bigint"></a>Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)[]

Pole obsahující sekvenci čísel `from` , `from + 1` ,..., `to` .

## <a name="remarks"></a>Poznámky

Rozdíl mezi `from` a se `to` musí vejít do `Int` hodnoty.