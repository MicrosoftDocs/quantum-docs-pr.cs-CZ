---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: Operace PrepareSingleQubitIdentity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 1c8c161ec2eae73a81c46e7941af49145cde0493
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193620"
---
# <a name="preparesinglequbitidentity-operation"></a>Operace PrepareSingleQubitIdentity

Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Připraví qubit ve stavu maximálního smíšené.

Připraví zadaný qubit ve stavu $ \boldone/$2 použitím depolarizing kanálu $ $ \begin{align} \Omega (\rho) \mathrel{: =} \frac {1} {4} \ sum_ {\mu \in \{ 0, 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}, \end{align} $ $ where $ \sigma \_ i $ je $i $ th Pauli a kde $ \rho $ je operátor hustoty představující smíšený stav.

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a>Vstup

### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, jehož stav má být depolarizace způsobem popsaným výše.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Smíšený stav $ \boldone/$2 popisující výsledek použití této operace na stav implicitně popisuje očekávanou hodnotu nad náhodnými možnostmi provedenými v této operaci.
Pro každou jednotlivou aplikaci tedy tato operace mapuje čistě stavy do čistého stavu, ale funguje tak, jak je popsáno v tématu očekávání.
Konkrétně tuto operaci lze použít v procesu tomography k měření *nejednotkových* komponent kanálu.