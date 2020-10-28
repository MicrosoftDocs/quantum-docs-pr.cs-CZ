---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Uživatelem definovaný typ SyndromeMeasOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 1314e16d26c7310bab21caa91cb398d4b6f09b29
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697908"
---
# <a name="syndromemeasop-user-defined-type"></a>Uživatelem definovaný typ SyndromeMeasOp

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček [](https://nuget.org/packages/)


Představuje operaci, která slouží k měření Syndrome bloku kódu chyby.

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a>Poznámky

Signatura `(LogicalRegister => Syndrome)` představuje operaci, která funguje společně na qubits v `LogicalRegister` a některých pomocných qubits následovaných měřením pomocných qubitsů k extrakci `Syndrome` hodnoty představující `Result[]` Tato měření.

## <a name="see-also"></a>Viz také

- [Microsoft. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. ErrorCorrection. Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)