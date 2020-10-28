---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Sequence – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705784"
---
# <a name="sequencel-function"></a>Sequence – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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