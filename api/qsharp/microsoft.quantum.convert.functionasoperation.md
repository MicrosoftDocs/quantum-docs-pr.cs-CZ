---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833826"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation – funkce

Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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