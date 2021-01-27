---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: Operace EstimateImagOverlapBetweenStates
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: f18ce43f9e5ebada4c5cc0aeff1538ac640c7390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851874"
---
# <a name="estimateimagoverlapbetweenstates-operation"></a>Operace EstimateImagOverlapBetweenStates

Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vzhledem k tomu, že jednotlivé operace připravují kopie stavu, odhadne imaginární část překrytí mezi stavy, které jsou připraveny jednotlivými operacemi.

```qsharp
operation EstimateImagOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Vstup

### <a name="commonpreparation--qubit--unit--is-adj"></a>commonPreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace, která připraví pevný vstupní stav.


### <a name="preparation1--qubit--unit--is-adj--ctl"></a>preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

První z těchto dvou operací přípravy stavu, které mají být porovnány.


### <a name="preparation2--qubit--unit--is-adj--ctl"></a>preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Druhý ze dvou operací přípravení stavu, které mají být porovnány.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits, které jsou `commonPreparation` , `preparation1` a `preparation2` všechny Act.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Počet měření, která se mají použít při odhadování překrytí



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Poznámky

Tato operace používá test Hadamard k vyhledání imaginární části pro $ $ \begin{align} \braket{\psi | V ^ {\dagger} U | \psi} \end{align} $ $ kde $ \ket{\psi} $ je stav, který připravil `commonPreparation` , $U $ je jednotková reprezentace akce `preparation1` a kde $V $ odpovídá `preparation2` .

## <a name="references"></a>Reference

- Aharonov *et al.* [quant-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).

## <a name="see-also"></a>Viz také

- [Microsoft. proEstimateRealOverlapBetweenStates. Popis.](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [Microsoft. proEstimateOverlapBetweenStates. Popis.](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)