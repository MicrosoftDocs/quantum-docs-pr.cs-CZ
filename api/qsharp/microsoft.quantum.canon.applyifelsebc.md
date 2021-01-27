---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: Operace ApplyIfElseBC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: 6140a8382cbd00589d1aef99e004f71f5d9295a9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841824"
---
# <a name="applyifelsebc-operation"></a>Operace ApplyIfElseBC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje jednu ze dvou přidaných operací v závislosti na hodnotě klasického bitu.

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit is Ctl
```


## <a name="description"></a>Popis

V případě bitu `bit` použije operaci `trueOp` s `trueInput` jako vstup `bit` , pokud je `true` , a platí, `falseOp(falseInput)` kdy `bit` je `false` .

## <a name="input"></a>Vstup

### <a name="bit--bool"></a>bitová hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)

Logická hodnota, která určuje, zda `trueOp` nebo `falseOp` je použita.


### <a name="trueop--t--unit--is-ctl"></a>trueOp: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL

Ověřitelné operace, která má být použita `bit` , pokud je `true` .


### <a name="trueinput--t"></a>trueInput: 'T

Vstup, který má být k dispozici, `trueOp` Když `bit` je `true` .


### <a name="falseop--u--unit--is-ctl"></a>falseOp: U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL.

Ověřitelné operace, která má být použita `bit` , pokud je `false` .


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