---
uid: Microsoft.Quantum.Measurement.MResetY
title: Operace MResetY
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 2e41e76a46b68178a8a22b39131d6ca2a8c50b64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854641"
---
# <a name="mresety-operation"></a>Operace MResetY

Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Měří jeden qubit v ose Y a obnoví ho do pevného počátečního stavu po měření.

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a>Popis

Provede qubit měření v $Y $-základ a zajistí, že qubit se vrátí do $ \ket {0} $ za měřením.

## <a name="input"></a>Vstup

### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Jedna qubit, která se má změřit



## <a name="output--__invalidresult__"></a>Výstup: __neplatný <Result>__

Výsledek měření `target` v Pauli $Y $ základ.