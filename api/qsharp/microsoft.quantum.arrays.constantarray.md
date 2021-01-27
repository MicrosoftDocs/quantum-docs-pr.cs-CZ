---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846228"
---
# <a name="constantarray-function"></a>ConstantArray – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vytvoří pole s danou délkou se všemi elementy, které se rovnají dané hodnotě.

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a>Vstup

### <a name="length--int"></a>Délka: [int](xref:microsoft.quantum.lang-ref.int)

Délka nového pole


### <a name="value--t"></a>hodnota: t

Hodnota každého prvku nového pole.



## <a name="output--t"></a>Výstup: t []

Nové pole s délkou `length` , například každý prvek `value` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="example"></a>Příklad

Následující kód vytvoří pole 3 logických hodnot, každé se rovná `true` :

```qsharp
let array = ConstantArray(3, true);
```