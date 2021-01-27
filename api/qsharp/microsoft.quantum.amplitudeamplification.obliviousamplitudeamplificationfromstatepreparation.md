---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 873c436d4b8d8efc9dc61c2baba9b0e0f7f09fc2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845809"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a>ObliviousAmplitudeAmplificationFromStatePreparation – funkce

Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Oblivious zesílení amplitudy od Oracle po částečné odrazy.

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>Vstup

### <a name="phases--reflectionphases"></a>fáze: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Fáze částečných odrazů


### <a name="startstateoracle--deterministicstateoracle"></a>startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Jednotková databáze Oracle $A $, která připraví pomocný stav spuštění


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Jednotkový typ Oracle $O $ `ObliviousOracle` , který pracuje společně s pomocným a systémovým registrem


### <a name="idxflagqubit--int"></a>idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)

Index do registru příznaků s jedním qubit



## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Operace, která implementuje zesílení oblivious amplitud na základě částečných odrazů.

## <a name="remarks"></a>Poznámky

To ukládá přísnější podmínky pro formu pomocných stavů Start a target než v `AmpAmpObliviousByReflectionPhases` .
Předpokládá se, že $A \ket {0} \_ f\ket {0} \_ A = \ket{\Text{Start}} \_ {FA} $ připraví pomocný počáteční stav $ \ket{\Text{Start}} \_ {FA} $ z výpočetního základu $ \ket {0} \_ f\ket {0} $.
Předpokládá se, že cílový stav je označený jako $ \ket {1} \_ f $.
Předpokládá se, že \begin{align} O\ket {\ text {Start}} \_ {FA} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ text {cokoli}} \_ a\ket {\ text {Target}} \_ s u \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} pro některé jednotkové $U $.