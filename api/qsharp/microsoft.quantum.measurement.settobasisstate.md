---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Operace SetToBasisState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: 2612bfe488c830abd835be89b2f8ea6795abf675
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194147"
---
# <a name="settobasisstate-operation"></a>Operace SetToBasisState

Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Nastaví qubit na daný výpočetní stav na základě měření qubit a v případě potřeby použije bitovou překlopení.

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a>Vstup

### <a name="desired--__invalidresult__"></a>požadováno: __neplatné <Result>__

Základní stav, na který má být qubit nastaven.


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, jehož stav má být nastaven.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Jako neutrální v této operaci se volá `M(q)` hned po `SetToBasisState(result, q)` návratu `result` .