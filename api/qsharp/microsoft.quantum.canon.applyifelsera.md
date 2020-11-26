---
uid: Microsoft.Quantum.Canon.ApplyIfElseRA
title: Operace ApplyIfElseRA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical result.
ms.openlocfilehash: 3ebd09b1e5876ff397f3524ba828ba26a271e91e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218593"
---
# <a name="applyifelsera-operation"></a>Operace ApplyIfElseRA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje jednu ze dvou sousedících operací v závislosti na hodnotě klasického výsledku.

```qsharp
operation ApplyIfElseRA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj), zeroInput : 'T), (oneOp : ('U => Unit is Adj), oneInput : 'U)) : Unit is Adj
```


## <a name="description"></a>Popis

Výsledkem `result` je, že použije operaci `zeroOp` s `zeroInput` jako vstup `result` , pokud je rovna `Zero` , a platí při použití `oneOp(oneInput)` `result == One` .

## <a name="input"></a>Vstup

### <a name="result--__invalidresult__"></a>výsledek: __neplatné <Result>__

Výsledek měření použitý k určení, zda `zeroOp` nebo `oneOp` je použit.


### <a name="zeroop--t--unit--is-adj"></a>zeroOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace sousedících operací, která má být použita v případě `result == Zero` .


### <a name="zeroinput--t"></a>zeroInput: 'T

Vstup, který má být k dispozici v `zeroOp` případě `result == Zero` .


### <a name="oneop--u--unit--is-adj"></a>oneOp: jednotka U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

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