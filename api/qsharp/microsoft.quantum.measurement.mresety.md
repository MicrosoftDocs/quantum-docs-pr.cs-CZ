---
uid: Microsoft.Quantum.Measurement.MResetY
title: Operace MResetY
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 48aba7317d0e48d089ec6c4814efdee51bb8e2ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709082"
---
# <a name="mresety-operation"></a>Operace MResetY

Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)

Balíček [](https://nuget.org/packages/)


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