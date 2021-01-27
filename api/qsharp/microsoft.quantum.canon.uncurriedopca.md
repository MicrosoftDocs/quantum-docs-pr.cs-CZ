---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 910d8a3006a2f217888b791e479e10f9f1a6965e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840040"
---
# <a name="uncurriedopca-function"></a>UncurriedOpCA – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Funkce, která vrací operace, vrací novou operaci, která přijímá oba vstupy jako řazené kolekce členů.
Modifikátor `CA` označuje, že operace lze řídit a přiléhající.

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>Vstup

### <a name="curriedop--t---u--unit--is-adj--ctl"></a>curriedOp: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Funkce, která vrací operace.



## <a name="output--tu--unit--is-adj--ctl"></a>Výstup: (t, ' U) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Nová operace `op` , která `op(t, u)` je ekvivalentem `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ prvního argumentu funkce curryfikované
### <a name="u"></a>U

Typ druhého argumentu funkce curryfikované

## <a name="see-also"></a>Viz také

- [Microsoft. proUncurriedOp. Canon.](xref:Microsoft.Quantum.Canon.UncurriedOp)