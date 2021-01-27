---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: Operace RecoverCSS
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: c192abbdfd02b26fbdba7b11f51ed08bb1a2030f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853036"
---
# <a name="recovercss-operation"></a>Operace RecoverCSS

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Provede jeden znak opravy chyb pomocí kódu, který je popsán v `CSS` typu.

```qsharp
operation RecoverCSS (code : Microsoft.Quantum.ErrorCorrection.CSS, fnX : Microsoft.Quantum.ErrorCorrection.RecoveryFn, fnZ : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a>Vstup

### <a name="code--css"></a>kód: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

Chybná zpráva šablon stylů CSS – Oprava kódu zabaleného jako `CSS` typ popisuje kódování a dekódování dat a způsob, jakým se má měřit chyba Syndromes.


### <a name="fnx--recoveryfn"></a>fnX: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

A `RecoveryFn` který mapuje jednotlivé $X $ Error Syndrome na `Pauli[]` operace, které opraví zjištěnou chybu.


### <a name="fnz--recoveryfn"></a>fnZ: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

A `RecoveryFn` který mapuje jednotlivé $Z $ Error Syndrome na `Pauli[]` operace, které opraví zjištěnou chybu.


### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Pole qubits, kde je definován kód stabilizace.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft.. ErrorCorrection. CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)
- [Microsoft. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [Microsoft. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)