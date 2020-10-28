---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: Operace ApplyToEachCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: b24fbb8c7a1a55c0a7750c5d096a61f4824dadfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704960"
---
# <a name="applytoeachca-operation"></a>Operace ApplyToEachCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje jednu qubit operaci na každý prvek v registru.
Modifikátor `CA` označuje, že operace s jedním qubit je ovladatelné a přiléhající.

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="singleelementoperation--t--unit-adj--ctl"></a>singleElementOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operace, která se má použít u každého qubit


### <a name="register--t"></a>registr: t []

Pole qubits, na které se má použít daná operace



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Cíl, na kterém operace funguje.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToEach. Canon.](xref:Microsoft.Quantum.Canon.ApplyToEach)