---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Operace MeasureWithScratch
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: c42316a811e0e4a81c7f244c093a2be88fe5c733
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227059"
---
# <a name="measurewithscratch-operation"></a>Operace MeasureWithScratch

Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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