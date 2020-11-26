---
uid: Microsoft.Quantum.Measurement.MResetX
title: Operace MResetX
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 04fb0f84ddf79a3d2cfc21fdaabd16c129f6d72f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194198"
---
# <a name="mresetx-operation"></a>Operace MResetX

Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Měří jeden qubit v ose X a obnoví ho do pevného počátečního stavu po měření.

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a>Popis

Provede qubit měření v $X $-základ a zajistí, že qubit se vrátí do $ \ket {0} $ za měřením.

## <a name="input"></a>Vstup

### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Jedna qubit, která se má změřit



## <a name="output--__invalidresult__"></a>Výstup: __neplatný <Result>__

Výsledek měření `target` v Pauli $X $ základ.