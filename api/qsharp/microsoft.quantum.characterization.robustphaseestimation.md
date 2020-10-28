---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: Operace RobustPhaseEstimation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: d04ee578c0e6f916e9a4da451075b79e0630c70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698713"
---
# <a name="robustphaseestimation-operation"></a>Operace RobustPhaseEstimation

Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)

Balíček [](https://nuget.org/packages/)


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

## <a name="references"></a>Odkazy

- Robustní kalibrace univerzálního Single-Qubit Gate-Set prostřednictvím robustního odhadu fáze Shelby Kimmel, Guang vystoupí hao nízká, Theodora J. Yoder https://arxiv.org/abs/1502.02677