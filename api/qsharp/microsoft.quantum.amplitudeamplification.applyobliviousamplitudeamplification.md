---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: Operace ApplyObliviousAmplitudeAmplification
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: a1bda344b1097c7ab3240bc6d9cd0d8df80b9662
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707743"
---
# <a name="applyobliviousamplitudeamplification-operation"></a>Operace ApplyObliviousAmplitudeAmplification

Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)

Balíček [](https://nuget.org/packages/)


Oblivious amplitudy tím, že se určí částečné odrazy.

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="phases--reflectionphases"></a>fáze: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Fáze částečných odrazů


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Operátor reflexe o počátečním stavu pomocného zápisu


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Operátor reflexe pro cílový stav pomocného zápisu


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Jednotkový typ Oracle $O $ `ObliviousOracle` , který pracuje společně na pomocných a systémových registrech.


### <a name="auxiliaryregister--qubit"></a>auxiliaryRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Pomocný registr


### <a name="systemregister--qubit"></a>systemRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Systémový registr



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

S ohledem na určitý pomocný stav spuštění $ \ket{\Text{Start}} \_ a $, konkrétní pomocný cílový stav $ \ket{\Text{Target}} a \_ $ a jakýkoli stav systému $ \ket{\psi} \_ s $, Předpokládejme, že \begin{align} O\ket {\ text {Start}} \_ a\ket {\ psí} \_ s = \lambda\ket{\Text{Target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\Text{Target} ^ \perp} \_ a\cdots \end{align} pro některé jednotkové $U $.
V rámci posloupnosti odrazů týkajících se stavů Start a target u pomocného registru, který prochází aplikace `signalOracle` a její sousedníci, pravděpodobnost úspěchu při použití U může být změněna.

Ve většině případů `auxiliaryRegister` je inicializován ve stavu $ \ket{\Text{Start}} \_ a $.

## <a name="references"></a>Odkazy

Seznamte se s 

- [ *D.W. bobuloviny, ráno dceřiné, r. Cleve, r. Kothari, R.D. Somma*](https://arxiv.org/abs/1312.1414) pro standardní verzi.
  Seznamte se s 
- [ *G.H. nízká, I.L. Čuangština*](https://arxiv.org/abs/1610.06546) pro generalizaci na částečná odrazy.