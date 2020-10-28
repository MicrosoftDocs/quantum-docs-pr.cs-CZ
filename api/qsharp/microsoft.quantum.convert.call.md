---
uid: Microsoft.Quantum.Convert.Call
title: Operace volání
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 8630f846b4b9823ce1c1dfd61dc8ca81e468517d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698312"
---
# <a name="call-operation"></a>Operace volání

Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)

Balíček [](https://nuget.org/packages/)


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