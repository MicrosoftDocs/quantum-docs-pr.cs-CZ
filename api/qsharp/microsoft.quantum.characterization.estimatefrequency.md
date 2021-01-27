---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: Operace EstimateFrequency
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 1e044a08718e02d673edab1d6b9d16d7f09618dc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851881"
---
# <a name="estimatefrequency-operation"></a>Operace EstimateFrequency

Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


S ohledem na přípravu a měření odhadne četnost, s jakou měření `Zero` probíhají (vrátí), provedením daného počtu testů.

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Vstup

### <a name="preparation--qubit--unit"></a>Příprava: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace $P $, která ve svém vstupním registru připraví daný stav $ \rho $.


### <a name="measurement--qubit--__invalidresult__"></a>měření: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __neplatné <Result>__ 

Operace $M $ představuje měření zájmu.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits, na které se každý působí přípravek a měření.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Počet, kolikrát by měla být provedena měření, aby se mohla odhadnout frekvence zájmu.



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)

Odhad $ \hat{p} $ frekvence, se kterou $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ vrátí `Zero` , získaný pomocí nevyváženého binomického Estimator $ \hat{p} = n \_ {\uparrow}/n \_ {\Text{Measurements}} $, kde $n \_ {\uparrow} $ je počet `Zero` zjištěných výsledků.

To je důležité zejména u cílových počítačů, které jsou v souladu s fyzickými omezeními, což znamená, že pravděpodobnosti nelze změřit.