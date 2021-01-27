---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Operace PrepareIdentity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: ec7e813110ccd9e6d499fc469fa27249a182b870
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855873"
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