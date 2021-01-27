---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: Operace EstimateFrequencyA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 6cca8dff70283e0d69441db8a5b31fb5bfb3082a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839912"
---
# <a name="estimatefrequencya-operation"></a>Operace EstimateFrequencyA

Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


S ohledem na přípravu, která je sousední a měření, odhadne četnost, s jakou měření vychází (vrátí `Zero` ) provedením daného počtu zkušebních hodnot.

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Vstup

### <a name="preparation--qubit--unit--is-adj"></a>Příprava: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace s sousedícím objektem $P $, která připraví daný stav $ \rho $ na vstupním registru.


### <a name="measurement--qubit--__invalidresult__"></a>měření: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __neplatné <Result>__ 

Operace $M $ představuje měření zájmu.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits, na které se každý působí přípravek a měření.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Počet, kolikrát by měla být provedena měření, aby se mohla odhadnout frekvence zájmu.



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)

Odhad $ \hat{p} $ frekvence, se kterou $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ vrátí `Zero` , získaný pomocí nevyváženého binomického Estimator $ \hat{p} = n \_ {\uparrow}/n \_ {\Text{Measurements}} $, kde $n \_ {\uparrow} $ je počet `Zero` zjištěných výsledků.

## <a name="remarks"></a>Poznámky

U sousedních operací lze určit určité předpoklady, jako je například volání operace, připraví qubits na přesně stejný stav, což umožňuje cílovým počítačům provádět některé optimalizace výkonu.