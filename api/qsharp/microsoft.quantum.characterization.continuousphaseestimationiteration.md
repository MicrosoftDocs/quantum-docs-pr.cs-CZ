---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: Operace ContinuousPhaseEstimationIteration
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 925b9040f6d9cda074b18a6f9079ccb653f9fa98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851897"
---
# <a name="continuousphaseestimationiteration-operation"></a>Operace ContinuousPhaseEstimationIteration

Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Provádí jednu iteraci iteračního (klasického) algoritmu fáze odhadu pomocí libovolného reálného výkonu jednotkové databáze Oracle.

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="oracle--continuousoracle"></a>Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

Operace funguje na dvojitém $t $ a v registru, jako je $U ^ t $ se u daného registru používá, kde $U $ je jednotná, jejíž fáze se má odhadnout, a kde $t $ je celočíselný výkon, který je pro Oracle přidělený.


### <a name="time--double"></a>čas: [Double](xref:microsoft.quantum.lang-ref.double)

Počet, kolikrát se má daný jednotkový Oracle použít.


### <a name="theta--double"></a>théta: [Double](xref:microsoft.quantum.lang-ref.double)

Úhel, o který se má Invertovat fáze v qubit ovládacího prvku před tím, než se bude chovat v cílovém stavu.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr stavu, na základě kterého společnost Oracle přijala.


### <a name="controlqubit--qubit"></a>controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

