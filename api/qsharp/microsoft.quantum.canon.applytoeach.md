---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Operace ApplyToEach
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: e1625829e2e9efd9d39fe0692f01c1cbbffc651c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704984"
---
# <a name="applytoeach-operation"></a>Operace ApplyToEach

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje jednu qubit operaci na každý prvek v registru.

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="singleelementoperation--t--unit"></a>singleElementOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, která se má použít u každého qubit


### <a name="register--t"></a>registr: t []

Pole qubits, na které se má použít daná operace



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Cíl, na kterém operace funguje.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToEachC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [Microsoft. proApplyToEachA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [Microsoft. proApplyToEachCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToEachCA)