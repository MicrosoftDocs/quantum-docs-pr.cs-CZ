---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: b953fb8f5737956e8597cd90a7d6bfc0bafce4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835625"
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