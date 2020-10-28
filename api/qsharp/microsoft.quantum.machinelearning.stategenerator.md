---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: Uživatelem definovaný typ StateGenerator
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: e3026dbae7209acd41924c0038a6f9b2c4b41197
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707965"
---
# <a name="stategenerator-user-defined-type"></a>Uživatelem definovaný typ StateGenerator

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček [](https://nuget.org/packages/)


Popisuje operaci, která připraví daný vstup na sekvenční třídění.

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Pojmenované položky

### <a name="nqubits--int"></a>NQubits: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits, na kterých je definován kódovaný vstup.
### <a name="prepare--littleendian--unit-adj--ctl"></a>Příprava: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operace, která připraví kódovaný vstup v registru s malým počtem endian `NQubits` qubits.