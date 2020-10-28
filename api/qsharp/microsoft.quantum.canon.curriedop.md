---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 13bc3e195d8a4ba26b726f96e4dc6b83da43c3e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704281"
---
# <a name="curriedop-function"></a>CurriedOp – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vrátí curryfikované verzi operace se dvěma vstupy.

To znamená, že vzhledem k operaci se dvěma vstupy Tato funkce použije Curry isomorphism $f (x, y) \equiv f (x) (y) $ a vrátí operaci jednoho vstupu, který vrátí operaci jednoho vstupu.

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a>Vstup

### <a name="op--tu--unit"></a>op: (t, ' U) => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, jejíž vstup je pár.



## <a name="output--t---u--unit"></a>Výstup: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, která přijímá první prvek páru a vrátí operaci, která přijímá jako svůj vstup druhý prvek vstupu původní operace.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ první součásti funkce definované na dvojicích.
### <a name="u"></a>U

Typ druhé komponenty funkce definované na dvojicích.

## <a name="remarks"></a>Poznámky

Následují ekvivalenty:

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```