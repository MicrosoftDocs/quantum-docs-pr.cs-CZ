---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: Operace ApplyIfElseBA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: 74d43344481c5a808e84ce9c9e36fa3e83cd0d89
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218661"
---
# <a name="applyifelseba-operation"></a>Operace ApplyIfElseBA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje jednu ze dvou sousedících operací v závislosti na hodnotě klasického bitu.

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit is Adj
```


## <a name="description"></a>Popis

V případě bitu `bit` použije operaci `trueOp` s `trueInput` jako vstup `bit` , pokud je `true` , a platí, `falseOp(falseInput)` kdy `bit` je `false` .

## <a name="input"></a>Vstup

### <a name="bit--bool"></a>bitová hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)

Logická hodnota, která určuje, zda `trueOp` nebo `falseOp` je použita.


### <a name="trueop--t--unit--is-adj"></a>trueOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace sousedících, která se má použít `bit` , pokud je `true` .


### <a name="trueinput--t"></a>trueInput: 'T

Vstup, který má být k dispozici, `trueOp` Když `bit` je `true` .


### <a name="falseop--u--unit--is-adj"></a>falseOp: jednotka U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace sousedících, která se má použít `bit` , pokud je `false` .


### <a name="falseinput--u"></a>falseInput: ' U

Vstup, který má být k dispozici, `falseOp` Když `bit` je `false` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace `trueOp` , která se má podmíněně použít.
### <a name="u"></a>U

Vstupní typ operace `falseOp` , která se má podmíněně použít.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyIfZero. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. proApplyIfOne. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. proApplyIfElseRC. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. proApplyIfElseRA. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. proApplyIfElseRCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)