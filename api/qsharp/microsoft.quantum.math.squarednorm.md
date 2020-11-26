---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: ecbc66a8851f23187e0c0ea53ce121442323733b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227297"
---
# <a name="squarednorm-function"></a>SquaredNorm – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí čtvercovou 2-normu vektoru.

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a>Popis

Vrátí čtvercovou 2-normu vektoru; To znamená, že zadané zadáním $ \vec{x} $ vrátí $ \ sum_i x_i ^ 2 $.

## <a name="input"></a>Vstup

### <a name="array--double"></a>Array: [Double](xref:microsoft.quantum.lang-ref.double)[]

Vektor, jehož čtvercová 2-norma se má vrátit.



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)

Druhá 2 – norma `array` .