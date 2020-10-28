---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698789"
---
# <a name="uncurriedopca-function"></a>UncurriedOpCA – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Funkce, která vrací operace, vrací novou operaci, která přijímá oba vstupy jako řazené kolekce členů.
Modifikátor `CA` označuje, že operace lze řídit a přiléhající.

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>Vstup

### <a name="curriedop--t---u--unit-ctl--adj"></a>curriedOp: t-> ' U [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL a ADJ

Funkce, která vrací operace.



## <a name="output--tu--unit-ctl--adj"></a>Výstup: (ne, ' U) [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ

Nová operace `op` , která `op(t, u)` je ekvivalentem `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ prvního argumentu funkce curryfikované
### <a name="u"></a>U

Typ druhého argumentu funkce curryfikované

## <a name="see-also"></a>Viz také

- [Microsoft. proUncurriedOp. Canon.](xref:Microsoft.Quantum.Canon.UncurriedOp)