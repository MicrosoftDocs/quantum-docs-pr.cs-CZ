---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: f811347d65a6460690163e9df631979c906bd89f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840769"
---
# <a name="curriedop-function"></a>CurriedOp – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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