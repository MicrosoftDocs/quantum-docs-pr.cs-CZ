---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839596"
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