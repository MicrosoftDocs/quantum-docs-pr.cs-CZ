---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Operace ApplyToEach
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 11f9363feb38676df3f805496c74036aa96160c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217862"
---
# <a name="applytoeach-operation"></a>Operace ApplyToEach

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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