---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698792"
---
# <a name="uncurriedopc-function"></a>UncurriedOpC – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Funkce, která vrací operace, vrací novou operaci, která přijímá oba vstupy jako řazené kolekce členů.
Modifikátor `C` označuje, že operace lze řídit.

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a>Vstup

### <a name="curriedop--t---u--unit-ctl"></a>curriedOp: t-> ' U [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL

Funkce, která vrací operace.



## <a name="output--tu--unit-ctl"></a>Výstup: (t, ' U) [=> CTL](xref:microsoft.quantum.lang-ref.unit)

Nová operace `op` , která `op(t, u)` je ekvivalentem `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ prvního argumentu funkce curryfikované
### <a name="u"></a>U

Typ druhého argumentu funkce curryfikované

## <a name="see-also"></a>Viz také

- [Microsoft. proUncurriedOp. Canon.](xref:Microsoft.Quantum.Canon.UncurriedOp)