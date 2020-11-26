---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Uživatelem definovaný typ SyndromeMeasOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 65e47d82546b1df0beec2c00f435d3e7a28e6ae6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200250"
---
# <a name="syndromemeasop-user-defined-type"></a>Uživatelem definovaný typ SyndromeMeasOp

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje operaci, která slouží k měření Syndrome bloku kódu chyby.

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a>Poznámky

Signatura `(LogicalRegister => Syndrome)` představuje operaci, která funguje společně na qubits v `LogicalRegister` a některých pomocných qubits následovaných měřením pomocných qubitsů k extrakci `Syndrome` hodnoty představující `Result[]` Tato měření.

## <a name="see-also"></a>Viz také

- [Microsoft. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. ErrorCorrection. Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)