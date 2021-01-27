---
uid: Microsoft.Quantum.Convert.Call
title: Operace volání
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 93458d08aa83ffa8b7b33de8bf51c970af291db9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850195"
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