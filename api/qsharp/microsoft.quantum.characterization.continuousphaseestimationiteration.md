---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: Operace ContinuousPhaseEstimationIteration
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: a3914a4b19e3b898b6de8808699da09d386f487a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698753"
---
# <a name="continuousphaseestimationiteration-operation"></a>Operace ContinuousPhaseEstimationIteration

Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)

Balíček [](https://nuget.org/packages/)


Provádí jednu iteraci iteračního (klasického) algoritmu fáze odhadu pomocí libovolného reálného výkonu jednotkové databáze Oracle.

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
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

