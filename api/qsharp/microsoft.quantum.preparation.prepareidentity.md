---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Operace PrepareIdentity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: 6e0a43e61e3c49edef94db63f07ed29132d84c83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210433"
---
# <a name="prepareidentity-operation"></a>Operace PrepareIdentity

Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


V případě registru připraví tento registr do smíšeného stavu.

Registr se připravuje ve stavu $ \boldone/2 ^ N $ tím, že použije kompletní kanál depolarizing na každou qubit, kde $N $ je délka registru.

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr, jehož stav má být depolarizace způsobem popsaným výše.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. Přípravno. Preparation. PrepareSingleQubitIdentity](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)