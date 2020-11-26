---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 92d7deb7010791e7de3d22ad4616b20110d5e84e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214377"
---
# <a name="expandedcoefficients-function"></a>ExpandedCoefficients – funkce

Obor názvů: [Microsoft. JordanWigner. chemie.. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Rozbalí kompaktní reprezentace Jordan-Wignerných koeficientů, aby bylo možné získat mapování 1:1 mezi těmito a Pauli podmínkami.

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a>Vstup

### <a name="coeff--double"></a>coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]

Pole koeficientů, které je čteno z Jordan-Wigner struktury dat Hamiltonian.


### <a name="termtype--int"></a>termType: [int](xref:microsoft.quantum.lang-ref.int)

Typ Jordan-Wigner podmínky.



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)[]

Rozšířená pole koeficientů, jedna na Pauli termín.