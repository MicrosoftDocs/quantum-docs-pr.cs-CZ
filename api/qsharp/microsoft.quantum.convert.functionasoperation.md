---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698305"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation – funkce

Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)

Balíček [](https://nuget.org/packages/)


Převede funkce na operace.

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a>Popis

V případě funkce vrátí operaci, která volá tuto funkci, a která nedělá nic jiného.

## <a name="input"></a>Vstup

### <a name="fn--input---output"></a>FN: výstup Input->

Funkce, která má být převedena na operaci.



## <a name="output--input--output"></a>Výstup: Input => – výstup 

Operace `op` , která `op(input)` je stejná jako `fn(input)` u všech `input` .

## <a name="type-parameters"></a>Parametry typu

### <a name="input"></a>Vstup

Typ vstupu funkce, která má být převedena.
### <a name="output"></a>Výstup

Typ výstupu funkce, která má být převedena.

## <a name="remarks"></a>Poznámky

To je užitečné hlavně při předávání funkcí funkcí nebo operací, které očekávají operaci jako vstup.