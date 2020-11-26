---
uid: Microsoft.Quantum.Simulation.AdiabaticStateEnergyUnitary
title: Operace AdiabaticStateEnergyUnitary
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AdiabaticStateEnergyUnitary
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: a69eb29318a750bea9c7c84ae4f90f7a31007c33
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225529"
---
# <a name="adiabaticstateenergyunitary-operation"></a>Operace AdiabaticStateEnergyUnitary

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Provede přípravu stavu pomocí `statePrepUnitary` příkazu ve stavu vstupu, následovaným přípravou stavu adiabatic pomocí a `adiabaticUnitary` , a konečně odhadem fáze s ohledem na `qpeUnitary` výsledný stav pomocí `phaseEstAlgorithm` .

```qsharp
operation AdiabaticStateEnergyUnitary (statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double), qubits : Qubit[]) : Double
```


## <a name="input"></a>Vstup

### <a name="stateprepunitary--qubit--unit"></a>statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Oracle představující stavovou přípravu počátečního dynamického generátoru.


### <a name="adiabaticunitary--qubit--unit"></a>adiabaticUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Oracle představující algoritmus vývoje adiabatic, který se použije k implementaci Sweep do konečného stavu algoritmu.


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a>qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Oracle reprezentující jednotkový operátor $U $ představující vývoj pro čas $ \delta t $ v rámci dynamického generátoru s uzemněným stavem $ \ket{\phi} $ a pozemní energie $E = \phi \\ , \delta t $.


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double) 

Operace, která provádí odhad fáze pro danou jednotkovou operaci.
Další podrobnosti najdete v tématu [odhad iterativní fáze](/quantum/libraries/characterization#iterative-phase-estimation) .


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr qubits, který se má použít k provedení simulace.



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)

Odhad $ \hat{\phi} $ pro stav energie $ \phi $ generátoru, reprezentovaný $U $.