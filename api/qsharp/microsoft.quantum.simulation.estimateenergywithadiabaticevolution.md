---
uid: Microsoft.Quantum.Simulation.EstimateEnergyWithAdiabaticEvolution
title: Operace EstimateEnergyWithAdiabaticEvolution
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergyWithAdiabaticEvolution
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: b279d35418b8f013ad0d72e9a980c9bf6ce0689a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225325"
---
# <a name="estimateenergywithadiabaticevolution-operation"></a>Operace EstimateEnergyWithAdiabaticEvolution

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Provede přípravu stavu pomocí `statePrepUnitary` příkazu na automaticky přidělený stav vstupu následovaný přípravou stavu adiabatic s využitím `adiabaticUnitary` a nakonec odhadem fáze s ohledem na `qpeUnitary` výsledný stav pomocí `phaseEstAlgorithm` .

```qsharp
operation EstimateEnergyWithAdiabaticEvolution (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a>Vstup

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits použitých pro simulaci.


### <a name="stateprepunitary--qubit--unit"></a>statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Oracle představující stavovou přípravu počátečního dynamického generátoru.


### <a name="adiabaticunitary--qubit--unit"></a>adiabaticUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Oracle představující algoritmus vývoje adiabatic, který se použije k implementaci Sweep do konečného stavu algoritmu.


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a>qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Oracle reprezentující jednotkový operátor $U $ představující vývoj pro čas $ \delta t $ v rámci dynamického generátoru s uzemněným stavem $ \ket{\phi} $ a pozemní energie $E = \phi \\ , \delta t $.


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double) 

Operace, která provádí odhad fáze pro danou jednotkovou operaci.
Další podrobnosti najdete v tématu [odhad iterativní fáze](/quantum/libraries/characterization#iterative-phase-estimation) .



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)

Odhad $ \hat{\phi} $ pro stav energie $ \phi $ generátoru, reprezentovaný $U $.