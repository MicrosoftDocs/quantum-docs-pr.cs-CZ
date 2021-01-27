---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Operace ApplyFixedPointAmplification
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: fa19c3bb06ae91a2fa18acb6f853020830e749f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847230"
---
# <a name="applyfixedpointamplification-operation"></a>Operace ApplyFixedPointAmplification

Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fixed-Point algoritmus zesílení amplitudy

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="statepreporacle--stateoracle"></a>statePrepOracle: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Jednotkový Oracle, který připraví stav spuštění.


### <a name="startqubits--qubit"></a>startQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit registraci



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

StartQubits musí být ve stavu $ \ket{0 \cdots 0} $. Tato operace provede iteraci několika dotazů v rámci pravomoci $2 $, dokud nedosáhnete maximálního počtu dotazů, nebo pokud cílový stav není nalezen.