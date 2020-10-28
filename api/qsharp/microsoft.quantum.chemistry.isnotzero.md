---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 3c0f9c6695e8c9ec4a0953d5217c28c512ac7de1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698681"
---
# <a name="isnotzero-function"></a>IsNotZero – funkce

Obor názvů: [Microsoft.. chemie](xref:Microsoft.Quantum.Chemistry)

Balíček [](https://nuget.org/packages/)


Ověří, zda `Double` je číslo nepřibližně nula.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Vstup

### <a name="number--double"></a>Number: [Double](xref:microsoft.quantum.lang-ref.double)

Číslo, které se má zkontrolovat



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

Vrátí hodnotu true `number` , pokud má absolutní hodnotu větší než `1e-15` .