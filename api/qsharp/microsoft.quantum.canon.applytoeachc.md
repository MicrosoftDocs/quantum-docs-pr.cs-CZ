---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Operace ApplyToEachC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: b8b51e1c8d52c140c3ca1e5a54d0bd4cf4873046
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850852"
---
# <a name="applytoeachc-operation"></a>Operace ApplyToEachC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje jednu qubit operaci na každý prvek v registru.
Modifikátor `C` označuje, že operace s jedním qubit je ovladatelné.

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a>Vstup

### <a name="singleelementoperation--t--unit--is-ctl"></a>singleElementOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL

Operace, která se má použít u každého qubit


### <a name="register--t"></a>registr: t []

Pole qubits, na které se má použít daná operace



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Cíl, na kterém operace funguje.

## <a name="example"></a>Příklad

Připravte tři-qubit $ \ket{+} $ stav:

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToEach. Canon.](xref:Microsoft.Quantum.Canon.ApplyToEach)