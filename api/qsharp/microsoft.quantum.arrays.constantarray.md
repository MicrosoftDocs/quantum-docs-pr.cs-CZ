---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210059"
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

