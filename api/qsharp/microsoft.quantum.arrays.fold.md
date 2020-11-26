---
uid: Microsoft.Quantum.Arrays.Fold
title: Funkce skládání
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: a42f9a832c18bd612c1ae416187f3f2513eed54d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221160"
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