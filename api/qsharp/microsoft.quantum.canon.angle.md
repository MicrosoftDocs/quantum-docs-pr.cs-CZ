---
uid: Microsoft.Quantum.Canon.Angle
title: Angle – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 0528f21b2d9c98b6497e28741964e6497d4d0fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842042"
---
# <a name="angle-function"></a>Angle – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

