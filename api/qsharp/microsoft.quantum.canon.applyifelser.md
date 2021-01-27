---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: Operace ApplyIfElseR
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 0d7cc9f67f9dd0c69a9256f007a3aeab3e457907
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841801"
---
# <a name="applyifelser-operation"></a>Operace ApplyIfElseR

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje jednu ze dvou operací v závislosti na hodnotě klasického výsledku.

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a>Popis

Výsledkem `result` je, že použije operaci `zeroOp` s `zeroInput` jako vstup `result` , pokud je rovna `Zero` , a platí při použití `oneOp(oneInput)` `result == One` .

## <a name="input"></a>Vstup

### <a name="result--__invalidresult__"></a>výsledek: __neplatné <Result>__

Výsledek měření použitý k určení, zda `zeroOp` nebo `oneOp` je použit.


### <a name="zeroop--t--unit"></a>zeroOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, která se má použít, když `result == Zero` .


### <a name="zeroinput--t"></a>zeroInput: 'T

Vstup, který má být k dispozici v `zeroOp` případě `result == Zero` .


### <a name="oneop--u--unit"></a>oneOp: [jednotka](xref:microsoft.quantum.lang-ref.unit) U => 

Operace, která se má použít, když `result == One` .


### <a name="oneinput--u"></a>oneInput: ' U

Vstup, který má být k dispozici v `oneOp` případě `result == One` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace `zeroOp` , která se má podmíněně použít.
### <a name="u"></a>U

Vstupní typ operace `oneOp` , která se má podmíněně použít.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyIfZero. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. proApplyIfOne. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. proApplyIfElseRC. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. proApplyIfElseRA. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. proApplyIfElseRCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)