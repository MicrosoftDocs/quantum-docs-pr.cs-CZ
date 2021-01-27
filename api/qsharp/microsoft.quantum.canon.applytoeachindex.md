---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: Operace ApplyToEachIndex
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 8b34dc24580a3df7ae2c13ef87a6fa10c7afd3f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844599"
---
# <a name="applytoeachindex-operation"></a>Operace ApplyToEachIndex

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje jednu operaci qubit na každý indexovaný element v registru.

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="singleelementoperation--intt--unit"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, která se má použít u každého qubit


### <a name="register--t"></a>registr: t []

Pole qubits, na které se má použít daná operace



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Cíl, na kterém každá operace funguje.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToEach. Canon.](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [Microsoft. proApplyToEachIndexA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [Microsoft. proApplyToEachIndexC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [Microsoft. proApplyToEachIndexCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)