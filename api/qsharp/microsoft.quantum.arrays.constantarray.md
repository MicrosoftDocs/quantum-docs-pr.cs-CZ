---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706137"
---
# <a name="constantarray-function"></a>ConstantArray – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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

