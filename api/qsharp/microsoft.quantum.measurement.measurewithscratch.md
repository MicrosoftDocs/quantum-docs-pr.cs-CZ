---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Operace MeasureWithScratch
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 1ee25dbccd5bddde406cf8ed84dff77d96d7804e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706745"
---
# <a name="measurewithscratch-operation"></a>Operace MeasureWithScratch

Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)

Balíček [](https://nuget.org/packages/)


Měří zadaný Pauli operátor pomocí explicitního qubitho škrábance k provedení měření.

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a>Vstup

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Qubit Pauli operátor, který jste zadali jako pole operátorů s jedním qubit Pauli.


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit registr, který se má změřit



## <a name="output--__invalidresult__"></a>Výstup: __neplatný <Result>__

Výsledek měření daného Pauli operátoru v `target` registru