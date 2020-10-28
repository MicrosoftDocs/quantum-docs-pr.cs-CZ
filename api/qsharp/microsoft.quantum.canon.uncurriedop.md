---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: 359c0b2a9dd56445fb39fadc6580809dd9fbf628
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698800"
---
# <a name="uncurriedop-function"></a>UncurriedOp – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


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