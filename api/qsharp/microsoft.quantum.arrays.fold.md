---
uid: Microsoft.Quantum.Arrays.Fold
title: Funkce skládání
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848610"
---
# <a name="fold-function"></a>Funkce skládání

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Opakuje funkci `f` prostřednictvím pole `array` a vrátí `f(f(f(initialState, array[0]), array[1]), ...)` .

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a>Vstup

### <a name="folder--statet---state"></a>Složka: (' State, t)-> ' State

Funkce, která má být přeložena v poli.


### <a name="state--state"></a>stav: stav

Počáteční stav složky.


### <a name="array--t"></a>Array: t []

Pole hodnot, které se mají přeloží



## <a name="output--state"></a>Výstup: "State"

Konečný stav vrácený složkou po provedení iterace u všech prvků `array` .

## <a name="type-parameters"></a>Parametry typu

### <a name="state"></a>Stav

Typ stavu, na kterém `folder` funkce pracuje, tj., přijímá jako první argument a vrací.
### <a name="t"></a>'S

Typ `array` prvků.

## <a name="example"></a>Příklad

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```