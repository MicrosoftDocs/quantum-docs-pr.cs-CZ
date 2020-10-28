---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Operace MResetZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 9f084b03504deea9fcf25e4c797c4bde3c97a995
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697604"
---
# <a name="mresetz-operation"></a>Operace MResetZ

Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)

Balíček [](https://nuget.org/packages/)


Měří jeden qubit v rámci a obnoví ho do pevného počátečního stavu po měření.

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a>Popis

Provede qubit měření v $Z $-základ a zajistí, že qubit se vrátí do $ \ket {0} $ za měřením.

## <a name="input"></a>Vstup

### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Jedna qubit, která se má změřit



## <a name="output--__invalidresult__"></a>Výstup: __neplatný <Result>__

Výsledek měření `target` v Pauli $Z $ základ.