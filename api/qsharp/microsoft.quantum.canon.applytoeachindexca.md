---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Operace ApplyToEachIndexCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: c5bb61aadbdaab9c74a3dcd418088c532b495ff5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704937"
---
# <a name="applytoeachindexca-operation"></a>Operace ApplyToEachIndexCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje jednu operaci qubit na každý indexovaný element v registru.
Modifikátor `CA` označuje, že operace s jedním qubit je sousední a ovladatelné.

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="singleelementoperation--intt--unit-adj--ctl"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operace, která se má použít u každého qubit


### <a name="register--t"></a>registr: t []

Pole qubits, na které se má použít daná operace



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Cíl, na kterém každá operace funguje.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToEachIndex. Canon.](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)