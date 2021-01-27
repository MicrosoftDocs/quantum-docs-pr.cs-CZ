---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: Operace EstimateOverlapBetweenStates
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: e083d6da13b0780905bf365c7a428ebc9666ce9e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839715"
---
# <a name="estimateoverlapbetweenstates-operation"></a>Operace EstimateOverlapBetweenStates

Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vzhledem k tomu, že jednotlivé operace připravují kopie stavu, odhaduje se čtvercový překryv mezi stavy, které jsou připraveny jednotlivými operacemi.

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Vstup

### <a name="preparation1--qubit--unit--is-adj"></a>preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

První z těchto dvou operací přípravy stavu, které mají být porovnány.


### <a name="preparation2--qubit--unit--is-adj"></a>preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Druhý ze dvou operací přípravení stavu, které mají být porovnány.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits, které jsou `commonPreparation` , `preparation1` a `preparation2` všechny Act.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Počet měření, která se mají použít při odhadování překrytí



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Poznámky

Tato operace používá test prohození k vyhledání $ $ \begin{align} \left | \braket{00\cdots 0 | V ^ {\dagger} U | 00 \ cdots 0} \right | ^ 2 \end{align} $ $, kde $U $ je jednotková reprezentace akce `preparation1` a kde $V $ odpovídá `preparation2` .

## <a name="see-also"></a>Viz také

- [Microsoft. proEstimateRealOverlapBetweenStates. Popis.](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [Microsoft. proEstimateImagOverlapBetweenStates. Popis.](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)