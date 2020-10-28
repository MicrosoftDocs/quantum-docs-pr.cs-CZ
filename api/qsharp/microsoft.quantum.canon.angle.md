---
uid: Microsoft.Quantum.Canon.Angle
title: Angle – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: da3ecdaf1b2c88180bd2a660fac0b6e87b2cafa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705521"
---
# <a name="angle-function"></a>Angle – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vrátí hodnotu 1, pokud `index` má lichý počet 1 a-1, pokud `index` má sudý počet 1.

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a>Popis

Hodnota odpovídá znaménku součinitele Rademacher-Walshho spektra n-Variable a funkce pro dané přiřazení, které určuje úhel otočení.

## <a name="input"></a>Vstup

### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)

Vstupní přiřazení jako celé číslo (od 0 do 2 ^ n-1)



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

