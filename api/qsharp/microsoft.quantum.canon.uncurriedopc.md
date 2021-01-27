---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 05df99dce8b167f32078ce256748647ceb94d0fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851994"
---
# <a name="uncurriedopc-function"></a>UncurriedOpC – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Funkce, která vrací operace, vrací novou operaci, která přijímá oba vstupy jako řazené kolekce členů.
Modifikátor `C` označuje, že operace lze řídit.

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a>Vstup

### <a name="curriedop--t---u--unit--is-ctl"></a>curriedOp: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL

Funkce, která vrací operace.



## <a name="output--tu--unit--is-ctl"></a>Výstup: (t, ' U) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL

Nová operace `op` , která `op(t, u)` je ekvivalentem `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ prvního argumentu funkce curryfikované
### <a name="u"></a>U

Typ druhého argumentu funkce curryfikované

## <a name="see-also"></a>Viz také

- [Microsoft. proUncurriedOp. Canon.](xref:Microsoft.Quantum.Canon.UncurriedOp)