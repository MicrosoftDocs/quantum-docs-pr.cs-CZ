---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: d9afb4b9b37b6cdd83bfd3829d3174d769c5f41b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211385"
---
# <a name="abscomplex-function"></a>AbsComplex – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí absolutní hodnotu komplexního čísla typu `Complex` .

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>Vstup

### <a name="input--complex"></a>vstup: [komplexní](xref:Microsoft.Quantum.Math.Complex)

Komplexní číslo $c = x + i y $.



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)

Absolutní hodnota $ | c | = \sqrt{x ^ 2 + y ^ 2} $.