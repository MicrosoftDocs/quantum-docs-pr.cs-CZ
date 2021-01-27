---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: d707b52bb17f4dea795fa4ff824c785e506b8b20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852011"
---
# <a name="uncurriedop-function"></a>UncurriedOp – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Funkce, která vrací operace, vrací novou operaci, která přijímá oba vstupy jako řazené kolekce členů.

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a>Vstup

### <a name="curriedop--t---u--unit"></a>curriedOp: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Funkce, která vrací operace.



## <a name="output--tu--unit"></a>Výstup: (t, ' U) => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Nová operace `op` , která `op(t, u)` je ekvivalentem `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ prvního vstupu k operaci curryfikované
### <a name="u"></a>U

Typ druhého vstupu na operaci curryfikované.

## <a name="see-also"></a>Viz také

- [Microsoft. proUncurriedOpC. Canon.](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [Microsoft. proUncurriedOpA. Canon.](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [Microsoft. proUncurriedOpCA. Canon.](xref:Microsoft.Quantum.Canon.UncurriedOpCA)