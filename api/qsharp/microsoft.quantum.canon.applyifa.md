---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: Operace ApplyIfA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: 8bdca1bf286d564dfbb540bc9d63c035d2196f00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845043"
---
# <a name="applyifa-operation"></a>Operace ApplyIfA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje v klasickém bitu operaci s sousedním objektem.

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a>Popis

`op`Pokud je zadaná operace a bitová hodnota `bit` , platí `op` pro `target` if `bit` `true` . `false`V případě, že se nic nestane s `target` .
Přípona `A` označuje, že operace, která se má použít, je sousední.

## <a name="input"></a>Vstup

### <a name="op--t--unit--is-adj"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace, která se má podmíněně použít


### <a name="bit--bool"></a>bitová hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)

logická hodnota, která určuje, zda je použita možnost op.


### <a name="target--t"></a>cíl: t

Vstup, na který se operace používá



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která se má podmíněně použít.

## <a name="example"></a>Příklad

Následující připraví registr qubits do výpočetního stavu, který je reprezentován klasickým bitem řetězce, který byl zadán jako pole `Bool` hodnot:

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyIfC. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [Microsoft. proApplyIfA. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [Microsoft. proApplyIfCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfCA)