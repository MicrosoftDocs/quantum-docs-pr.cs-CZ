---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Operace MResetZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: fc9ba6576b56d7df1a57334e1da46b9c48376ecb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853739"
---
# <a name="mresetz-operation"></a>Operace MResetZ

Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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