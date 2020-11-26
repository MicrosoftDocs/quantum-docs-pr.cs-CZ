---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: Operace ResetAll
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: d22ce607e8e5cb3a1c041dc1973875f2a0777d2b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198686"
---
# <a name="resetall-operation"></a>Operace ResetAll

Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Přihlaste se k poli qubits, změřte je a ujistěte se, že jsou ve stavu | 0 ⟩ tak, aby je bylo možné bezpečně uvolnit.

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Pole qubits, jehož stavy mají být obnoveny na $ \ket {0} $.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

