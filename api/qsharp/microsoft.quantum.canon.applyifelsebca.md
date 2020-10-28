---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: Operace ApplyIfElseBCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 0ebd086f4c8166a8d6b593200b0a3354c1420c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705328"
---
# <a name="applyifelsebca-operation"></a>Operace ApplyIfElseBCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje jednu ze dvou jednotkových operací v závislosti na hodnotě klasického bitu.

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit
```


## <a name="description"></a>Popis

V případě bitu `bit` použije operaci `trueOp` s `trueInput` jako vstup `bit` , pokud je `true` , a platí, `falseOp(falseInput)` kdy `bit` je `false` .

## <a name="input"></a>Vstup

### <a name="bit--bool"></a>bitová hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)

Logická hodnota, která určuje, zda `trueOp` nebo `falseOp` je použita.


### <a name="trueop--t--unit-adj--ctl"></a>trueOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Jednotná operace, která se má `bit` použít `true` , pokud je.


### <a name="trueinput--t"></a>trueInput: 'T

Vstup, který má být k dispozici, `trueOp` Když `bit` je `true` .


### <a name="falseop--u--unit-adj--ctl"></a>falseOp: ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Jednotná operace, která se má `bit` použít `false` , pokud je.


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