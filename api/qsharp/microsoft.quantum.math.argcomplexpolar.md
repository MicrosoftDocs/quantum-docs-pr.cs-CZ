---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 7088397bd60e2779ef60afc1bb7108d937a62c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195762"
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