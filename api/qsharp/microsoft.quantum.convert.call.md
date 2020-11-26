---
uid: Microsoft.Quantum.Convert.Call
title: Operace volání
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 92c159cef878fb587b0ed514fd6660dd19527cab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214207"
---
# <a name="call-operation"></a>Operace volání

Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Volá funkci s daným vstupem.

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a>Popis

Při zadání funkce a vstupu do této funkce volá funkci a vrátí její výstup.

## <a name="input"></a>Vstup

### <a name="fn--input---output"></a>FN: výstup Input->

Funkce, která má být volána.


### <a name="input--input"></a>Input: Input

Vstup, který má být předán do funkce.



## <a name="output--output"></a>Výstup: Output

Výsledek volání funkce `fn`.

## <a name="type-parameters"></a>Parametry typu

### <a name="input"></a>Vstup


### <a name="output"></a>Výstup



## <a name="remarks"></a>Poznámky

Tato operace je hlavně užitečná pro vynucení volání funkce na konkrétní místo v rámci operace nebo pro volání funkce, kde je očekávána operace.