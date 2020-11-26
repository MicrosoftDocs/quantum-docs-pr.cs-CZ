---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Operace Reset
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: 61b5e4ccdf009dcb6c639e3d8e23bc73a6e475b5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198669"
---
# <a name="reset-operation"></a>Operace Reset

Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


V případě jednoho qubitu je měří a zajišťuje, že je ve stavu | 0 ⟩, takže je možné ho bezpečně uvolnit.

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a>Vstup

### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, jehož stav má být resetován na $ \ket {0} $.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

