---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: Operace EstimateFrequency
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 83589637a7bfa328812207271844411f57d42097
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698756"
---
# <a name="estimatefrequency-operation"></a>Operace EstimateFrequency

Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)

Balíček [](https://nuget.org/packages/)


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