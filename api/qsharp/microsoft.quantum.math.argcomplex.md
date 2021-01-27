---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: e8ce73a43940ab0ed66338f962cc6f76fc2b694b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842759"
---
# <a name="argcomplex-function"></a>ArgComplex – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí fázi komplexního čísla typu `Complex` .

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>Vstup

### <a name="input--complex"></a>vstup: [komplexní](xref:Microsoft.Quantum.Math.Complex)

Komplexní číslo $c = x + i y $.



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)

Fáze $ \text{Arg} [c] = \text{ArcTan} (y, x) \in (-\pi, \pi] $.