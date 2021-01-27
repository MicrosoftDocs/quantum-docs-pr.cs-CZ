---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848213"
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