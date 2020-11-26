---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204058"
---
# <a name="isnotzero-function"></a>IsNotZero – funkce

Obor názvů: [Microsoft.. chemie](xref:Microsoft.Quantum.Chemistry)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Ověří, zda `Double` je číslo nepřibližně nula.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Vstup

### <a name="number--double"></a>Number: [Double](xref:microsoft.quantum.lang-ref.double)

Číslo, které se má zkontrolovat



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

Vrátí hodnotu true `number` , pokud má absolutní hodnotu větší než `1e-15` .