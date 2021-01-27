---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Operace ApplyToEachIndexCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: 5046edc54576420bd8919ca52947076aed17cbce
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850803"
---
# <a name="applytoeachindexca-operation"></a>Operace ApplyToEachIndexCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje jednu operaci qubit na každý indexovaný element v registru.
Modifikátor `CA` označuje, že operace s jedním qubit je sousední a ovladatelné.

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Operace, která se má použít u každého qubit


### <a name="register--t"></a>registr: t []

Pole qubits, na které se má použít daná operace



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Cíl, na kterém každá operace funguje.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToEachIndex. Canon.](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)