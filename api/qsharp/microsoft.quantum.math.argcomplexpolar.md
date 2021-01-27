---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 5809b5463e6bf8ee73d095dfe4eafedfbb5e0702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852903"
---
# <a name="argcomplexpolar-function"></a>ArgComplexPolar – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí fázi komplexního čísla typu `ComplexPolar` .

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a>Vstup

### <a name="input--complexpolar"></a>vstup: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Komplexní číslo $c = r e ^ {i t} $



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)

Fáze $ \text{Arg} [c] = t $.