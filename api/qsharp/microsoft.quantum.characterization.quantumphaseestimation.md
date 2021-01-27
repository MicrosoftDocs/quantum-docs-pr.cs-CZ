---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: Operace QuantumPhaseEstimation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 4bdf3de9dab20fa97ba47f15efec4b41a10709f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839657"
---
# <a name="quantumphaseestimation-operation"></a>Operace QuantumPhaseEstimation

Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Provádí pro daný Oracle algoritmus odhadu doby přírůstku `U` a `targetState` přečtení fáze do pokladny na základě služby big-endian.

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Operace implementující $U ^ m $ pro celou celočíselnou mocninu m.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr u, který představuje stav $ \ket{\phi} $, se v $U $. Pokud $ \ket{\phi} $ je eigenstate z $U $, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ for $ \phi \in [0, 2 \ pi) $ je neznámá fáze.


### <a name="controlregister--bigendian"></a>controlRegister: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Registr s celočíselnými vyjádřeními big-endian, který se dá použít k řízení poskytnutého Oracle a který bude obsahovat reprezentaci $ \phi $ za použití této operace. Předpokládá se, že controlRegister začíná v počátečním stavu $ \ket{00\cdots 0} $, kde délka registru označuje požadovanou přesnost.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

