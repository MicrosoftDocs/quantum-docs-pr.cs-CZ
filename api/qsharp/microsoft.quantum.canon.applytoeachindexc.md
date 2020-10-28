---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Operace ApplyToEachIndexC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 387d7ea24b9251386a71b42a1f51ce70933bf6fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704945"
---
# <a name="applytoeachindexc-operation"></a>Operace ApplyToEachIndexC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje jednu operaci qubit na každý indexovaný element v registru.
Modifikátor `C` označuje, že operace s jedním qubit je ovladatelné.

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="singleelementoperation--intt--unit-ctl"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) = seznam CTL>ch [jednotek](xref:microsoft.quantum.lang-ref.unit)

Operace, která se má použít u každého qubit


### <a name="register--t"></a>registr: t []

Pole qubits, na které se má použít daná operace



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Cíl, na kterém každá operace funguje.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToEachIndex. Canon.](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)