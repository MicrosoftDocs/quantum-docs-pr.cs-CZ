---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: cad508f166d4af805cb98cd21a0260d9babb6a4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204636"
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