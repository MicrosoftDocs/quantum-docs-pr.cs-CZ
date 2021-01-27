---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: Uživatelem definovaný typ JordanWignerInputState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 18adf28b4e99c825f14e9271791ded069e687901
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837697"
---
# <a name="jordanwignerinputstate-user-defined-type"></a>Uživatelem definovaný typ JordanWignerInputState

Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Formát dat předaných z C# na Q # představující přípravu počátečního stavu. význam zobrazených dat závisí na algoritmu, který ho přijímá.

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

