---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Operace ApplyToEach
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 61dda69751989ef8a98fa8fb01d832014ec4ad35
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844629"
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

## <a name="example"></a>Příklad

Připravte tři-qubit $ \ket{+} $ stav:

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToEachC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [Microsoft. proApplyToEachA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [Microsoft. proApplyToEachCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToEachCA)