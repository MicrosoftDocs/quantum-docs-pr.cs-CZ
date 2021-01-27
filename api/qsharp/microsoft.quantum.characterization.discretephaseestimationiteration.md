---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: Operace DiscretePhaseEstimationIteration
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 03e2300dcc2d2cb42992e074833c8cd2530e898b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839975"
---
# <a name="discretephaseestimationiteration-operation"></a>Operace DiscretePhaseEstimationIteration

Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Provádí jednu iteraci iteračního (klasického) algoritmu fáze odhadu pomocí celočíselné mocniny jednotkové databáze Oracle.

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Operace funguje na základě celého čísla a registru, například $U ^ m $ se u daného registru používá, kde $U $ je jednotkou, jejíž fáze má být odhadnuta, a kde $m $ je celočíselný výkon, který je dán pro Oracle.


### <a name="power--int"></a>napájení: [int](xref:microsoft.quantum.lang-ref.int)

Počet, kolikrát se má daný jednotkový Oracle použít.


### <a name="theta--double"></a>théta: [Double](xref:microsoft.quantum.lang-ref.double)

Úhel, o který se má Invertovat fáze v qubit ovládacího prvku před tím, než se bude chovat v cílovém stavu.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr stavu, na základě kterého společnost Oracle přijala.


### <a name="controlqubit--qubit"></a>controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Pomocný qubit použitý k řízení aplikace daného Oracle.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

