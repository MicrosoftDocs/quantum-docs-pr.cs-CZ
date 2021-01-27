---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: Operace ApplyMultiplyControlledLowDepthAnd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 0ad4b6eabcbbb63751489dd92a13a6673c1ae6b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841674"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a>Operace ApplyMultiplyControlledLowDepthAnd

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementuje Toffoli bránu s více řízenými hodnotami za předpokladu, že cílový qubit je inicializovaný 0.  Operace souseda předpokládá, že cílový qubit bude resetován na hodnotu 0.  Vyžaduje RZ hloubku 1, zatímco počet pomocných qubits je exponenciální v počtu qubits.

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a>Vstup

### <a name="controls--qubit"></a>ovládací prvky: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits ovládacího prvku


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Cílový qubit



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

