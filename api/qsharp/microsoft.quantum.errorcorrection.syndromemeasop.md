---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Uživatelem definovaný typ SyndromeMeasOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 36336f9e47e5f360cf5e19ffb6e15b4af88b2580
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850056"
---
# <a name="syndromemeasop-user-defined-type"></a>Uživatelem definovaný typ SyndromeMeasOp

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje operaci, která slouží k měření Syndrome bloku kódu chyby.

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a>Příklad

Syndromes míry pro překlápění kódu $S = \langle ZZI, IZZ \rangle $ použití pomocné qubits v případě, že je odolný proti chybám:

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a>Poznámky

Signatura `(LogicalRegister => Syndrome)` představuje operaci, která funguje společně na qubits v `LogicalRegister` a některých pomocných qubits následovaných měřením pomocných qubitsů k extrakci `Syndrome` hodnoty představující `Result[]` Tato měření.

## <a name="see-also"></a>Viz také

- [Microsoft. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. ErrorCorrection. Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)