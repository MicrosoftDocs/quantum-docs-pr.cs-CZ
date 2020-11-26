---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: Uživatelem definovaný typ StateGenerator
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: 5c9643f5c917ff3cb25fa8c046856b03cc287edd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211555"
---
# <a name="stategenerator-user-defined-type"></a>Uživatelem definovaný typ StateGenerator

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Popisuje operaci, která připraví daný vstup na sekvenční třídění.

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Pojmenované položky

### <a name="nqubits--int"></a>NQubits: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits, na kterých je definován kódovaný vstup.
### <a name="prepare--littleendian--unit--is-adj--ctl"></a>Příprava: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je ADJ + CTL

Operace, která připraví kódovaný vstup v registru s malým počtem endian `NQubits` qubits.