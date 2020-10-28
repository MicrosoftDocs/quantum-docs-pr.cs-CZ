---
uid: Microsoft.Quantum.Canon.ApplyIfElseRA
title: Operace ApplyIfElseRA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical result.
ms.openlocfilehash: d0181d98a9867f71d8a8f8dea4331e5a13f9e59c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705297"
---
# <a name="applyifelsera-operation"></a>Operace ApplyIfElseRA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje jednu ze dvou sousedících operací v závislosti na hodnotě klasického výsledku.

```qsharp
operation ApplyIfElseRA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj), zeroInput : 'T), (oneOp : ('U => Unit is Adj), oneInput : 'U)) : Unit
```


## <a name="description"></a>Popis

Výsledkem `result` je, že použije operaci `zeroOp` s `zeroInput` jako vstup `result` , pokud je rovna `Zero` , a platí při použití `oneOp(oneInput)` `result == One` .

## <a name="input"></a>Vstup

### <a name="result--__invalidresult__"></a>výsledek: __neplatné <Result>__

Výsledek měření použitý k určení, zda `zeroOp` nebo `oneOp` je použit.


### <a name="zeroop--t--unit-adj"></a>zeroOp: t [=> ADJ](xref:microsoft.quantum.lang-ref.unit)

Operace sousedících operací, která má být použita v případě `result == Zero` .


### <a name="zeroinput--t"></a>zeroInput: 'T

Vstup, který má být k dispozici v `zeroOp` případě `result == Zero` .


### <a name="oneop--u--unit-adj"></a>oneOp: ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ

Operace sousedících operací, která má být použita v případě `result == One` .


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