---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: Uživatelem definovaný typ JordanWignerInputState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 81993a7449098c03639cf090fb36ed39c6ba17c0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214683"
---
# <a name="jordanwignerinputstate-user-defined-type"></a>Uživatelem definovaný typ JordanWignerInputState

Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Formát dat předaných z C# na Q # představující přípravu počátečního stavu. význam zobrazených dat závisí na algoritmu, který ho přijímá.

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

