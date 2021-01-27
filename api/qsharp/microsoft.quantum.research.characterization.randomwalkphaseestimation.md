---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: Operace RandomWalkPhaseEstimation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: f9edafcce62c8b30a6bd52b7dbaa2df2c50c920d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846005"
---
# <a name="randomwalkphaseestimation-operation"></a>Operace RandomWalkPhaseEstimation

Obor názvů: [Microsoft.. Research. charakterizace](xref:Microsoft.Quantum.Research.Characterization)

Balíček: [Microsoft. Prohledávejte. Research. charakterizace](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)


Provádí odhad iterativní fáze pomocí náhodného prohledání přibližné bayesovského rozhodování odvození na výsledky klasických měření z daných Oracle a eigenstate.

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Vstup

### <a name="initialmean--double"></a>initialMean: [Double](xref:microsoft.quantum.lang-ref.double)

Střední hodnota počátečního normálního povýšení při předchozí distribuci přes $ \phi $


### <a name="initialstddev--double"></a>initialStdDev: [Double](xref:microsoft.quantum.lang-ref.double)

Směrodatná odchylka počátečního normálního rozdělení při předchozí distribuci na $ \phi $


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Počet měření, která se mají přijmout do konečného dodatečného odhadu.


### <a name="maxmeasurements--int"></a>maxMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Celkový počet měření, než může být proveden před tím, než je operace považována za neúspěšnou.


### <a name="unwind--int"></a>unwind: [int](xref:microsoft.quantum.lang-ref.int)

Počet výsledků, které mají být zapomenout při selhání kontroly konzistence.


### <a name="oracle--continuousoracle"></a>Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

Operace představující jednotnou $U $, kterou $U (t) \ket{\phi} = e ^ {i t \phi}\ket{\phi} $ for eigenstates $ \ket{\phi} $ s neznámou fází $ \phi \in \mathbb{R} ^ + $.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr, na kterém $U $ pracuje.



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)

Konečný odhad $ \hat{\phi} \mathrel{: =} \expect [\phi] $, kde se očekává, že je na začátku všechna přijatá data.

## <a name="remarks"></a>Poznámky

### <a name="iterative-phase-estimation-and-eigenstates"></a>Odhad iterační fáze a Eigenstates

Obecně platí, že vstupní registr `eigenstate` nemusí být eigenstate $ \ket{\phi} $ of $U $, ale může být na pozici nad eigenstates. Předpokládejme, že vstupní stav je dán \begin{align} \ket{\psi} & = \sum \_ {j} \Alpha \_ j \ket{\phi \_ j}, \end{align}, kde $ \{ \Alpha \_ j \} $ jsou složité, například $ \sum \_ j | \Alpha \_ j | ^ 2 = $1 a kde $U \ket{\phi \_ j} = \phi \_ j\ket {\ fí \_ j} $.

Následný odhad iterační fáze se nakonec konverguje na jeden eigenstate, jak je popsáno v příručce pro [vývoj](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).

### <a name="experiment-design"></a>Experimentovat návrh

Doba měření $t $ a inverze úhlů $ \theta $ předaná do `oracle` jsou zvolena v souladu s *heuristikou pro odhad částic*, \Begin{align} \theta \sim \Pr (\phi), \quad t \approx \frac {1} {\variance{\phi}}.
\end{align} tato heuristická metoda je ideální pro snížení očekávané další odchylky v iterativní fázi odhadu v rámci předběžného normálního předběžného.

### <a name="optimality"></a>Optimální výkon

Tato operace se blíží optimálnímu Estimator pro fázi $ \phi $, jak je vyhodnocená pomocí $L kvadratické ztráty (\phi, \hat{\phi}) \mathrel{: =} (\phi-\hat{\phi}) ^ 2 $.

Další informace o statistice iterativní fáze odhadu najdete v tématu [odhad fáze bayesovského rozhodování](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) .

## <a name="references"></a>Reference

- Pro trajekty *et al.* 2011 [doi: 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [arXiv: 1110.3067](https://arxiv.org/abs/1110.3067).
- Wiebe *et al.* 2013 [doi: 10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv: 1309.0876](https://arxiv.org/abs/1309.0876)
- Wiebe a granade 2018 *(v přípravě)*.