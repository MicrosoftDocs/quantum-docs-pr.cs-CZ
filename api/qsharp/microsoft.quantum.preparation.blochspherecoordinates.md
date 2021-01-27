---
uid: Microsoft.Quantum.Preparation.BlochSphereCoordinates
title: BlochSphereCoordinates – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: BlochSphereCoordinates
qsharp.summary: >-
  Computes the Bloch sphere coordinates for a single-qubit state.

  Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.
ms.openlocfilehash: 62643f64a6b829949fa708e300d9d262527dbb29
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855899"
---
# <a name="blochspherecoordinates-function"></a>BlochSphereCoordinates – funkce

Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vypočítá souřadnice sféry Bloch pro stav s jedním qubit.

Předaná dvě složitá čísla $a 0, a1 $, která představuje stav qubit, vypočítá souřadnice Bloch koule tak, že $a 0 \ket {0} + a1 \ket {1} = r e ^ {IT} (e ^ {-i \phi/2}\cos{(\ théta/2)} \ket {0} + e ^ {i \phi/2}\sin{(\ théta/2)} \ket {1} ) $.

```qsharp
function BlochSphereCoordinates (a0 : Microsoft.Quantum.Math.ComplexPolar, a1 : Microsoft.Quantum.Math.ComplexPolar) : (Microsoft.Quantum.Math.ComplexPolar, Double, Double)
```


## <a name="input"></a>Vstup

### <a name="a0--complexpolar"></a>a0: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Složitý koeficient stavu $ \ket {0} $


### <a name="a1--complexpolar"></a>a1: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Složitý koeficient stavu $ \ket {1} $



## <a name="output--complexpolardoubledouble"></a>Výstup: ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar),[Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))

Řazená kolekce členů obsahující `(ComplexPolar(r, t), phi, theta)` .