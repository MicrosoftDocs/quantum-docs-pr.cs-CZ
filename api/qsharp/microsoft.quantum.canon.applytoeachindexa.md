---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: Operace ApplyToEachIndexA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 0fe0697e6f1d9441c2d2ad2c7396f6da8daa0e1e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704952"
---
# <a name="applytoeachindexa-operation"></a>Operace ApplyToEachIndexA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje jednu operaci qubit na každý indexovaný element v registru.
Modifikátor `A` označuje, že operace s jedním qubit je sousední.

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="singleelementoperation--intt--unit-adj"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ.

Operace, která se má použít u každého qubit


### <a name="register--t"></a>registr: t []

Pole qubits, na které se má použít daná operace



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Cíl, na kterém každá operace funguje.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToEachIndex. Canon.](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)