---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: Operace ApplyToEachIndex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 4ce184b34add9238e26f9b35b40ec0bddb23ccf9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704953"
---
# <a name="applytoeachindex-operation"></a>Operace ApplyToEachIndex

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


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