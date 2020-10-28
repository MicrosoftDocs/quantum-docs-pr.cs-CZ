---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698793"
---
# <a name="uncurriedopa-function"></a>UncurriedOpA – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Funkce, která vrací operace, vrací novou operaci, která přijímá oba vstupy jako řazené kolekce členů.
Modifikátor `A` označuje, že operace jsou sousedící.

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a>Vstup

### <a name="curriedop--t---u--unit-adj"></a>curriedOp: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ

Funkce, která vrací operace.



## <a name="output--tu--unit-adj"></a>Výstup: (t, ' U) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ

Nová operace `op` , která `op(t, u)` je ekvivalentem `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ prvního argumentu funkce curryfikované
### <a name="u"></a>U

Typ druhého argumentu funkce curryfikované

## <a name="see-also"></a>Viz také

- [Microsoft. proUncurriedOp. Canon.](xref:Microsoft.Quantum.Canon.UncurriedOp)