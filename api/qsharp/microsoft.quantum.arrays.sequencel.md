---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Sequence – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 7e3c5c31428f9be152e28afbe478a3d15eb0a56c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850989"
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

## <a name="example"></a>Příklad

```qsharp
let arr1 = SequenceL(0L, 3L); // [0L, 1L, 2L, 3L]
let arr2 = SequenceL(23L, 29L); // [23L, 24L, 25L, 26L, 27L, 28L, 29L]
let arr3 = SequenceL(-5L, -2L); // [-5L, -4L, -3L, -2L]
```

## <a name="remarks"></a>Poznámky

Rozdíl mezi `from` a se `to` musí vejít do `Int` hodnoty.