---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: Operace RobustPhaseEstimation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 4b37c8275a5b2aee8534bacc5831281aa498b57d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851805"
---
# <a name="robustphaseestimation-operation"></a>Operace RobustPhaseEstimation

Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Provádí robustní neiterativní algoritmus odhadu neiteračních procesorů pro dané Oracle `U` a eigenstate a poskytuje jeden odhad ve fázi s proměnlivým škálováním v Heisenberg limitu.

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Vstup

### <a name="bitsprecision--int"></a>bitsPrecision: [int](xref:microsoft.quantum.lang-ref.int)

To poskytuje odhad $ \phi $ se směrodatnou odchylkou $ \sigma \le 2 \ pi/2 ^ \text{bitsPrecision} $ s použitím řady dotazů, které se mění jako $ \sigma \le 10,7 \pi/\Text{# dotazů} $.


### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Operace implementující $U ^ m $ pro celočíselné pravomoci $m $.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Každé z nich registruje, že $U $ funguje. Pokud ukládá eigenstate $ \ket{\phi} $ z $U $, pak $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ for $ \phi\in (-\pi, \pi] $ je neznámá fáze.



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Poznámky

V případě velkého počtu dotazů Cramer-Rao dolní meze směrodatné odchylky odhadu hodnot $ \phi $ re\text{$ \sigma \ge 2 \pi/# dotazů.

## <a name="references"></a>Reference

- Robustní kalibrace univerzálního Single-Qubit Gate-Set prostřednictvím robustního odhadu fáze Shelby Kimmel, Guang vystoupí hao nízká, Theodora J. Yoder https://arxiv.org/abs/1502.02677