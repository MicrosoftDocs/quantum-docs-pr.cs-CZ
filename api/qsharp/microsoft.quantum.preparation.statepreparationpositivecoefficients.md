---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationPositiveCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.


  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 8f1fd7d77531996faf566adb78f452929d6cbd50
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193246"
---
# <a name="statepreparationpositivecoefficients-function"></a>StatePreparationPositiveCoefficients – funkce

Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> StatePreparationPositiveCoefficients se už nepoužívá. <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD>Místo toho ho použijte.

Vrátí operaci, která připraví daný stav.

Vrácená operace $U $ připraví libovolný stav pro každý kraj $ \ket{\psi} $ s pozitivním koeficientem $ \ alpha_j \ge $0 ze stavu $n $-qubit výpočetního základu $ \ket{0...0} $.

Akce U nově přiděleného registru je dána $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.
\end{align} $ $

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Vstup

### <a name="coefficients--double"></a>koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]

Pole až do $2 ^ n $ koeficienty $ \ alpha_j $. $J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.



## <a name="output--littleendian--unit--is-adj--ctl"></a>Výstup: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je ADJ + CTL

Jednotná provozní operace pro přípravu stavu $U $.

## <a name="remarks"></a>Poznámky

Negativní vstupní koeficienty $ \ alpha_j < $0 budou považovány za kladné s hodnotou $ | \ alpha_j | $. `coefficients` budou doplněny elementy $ \ alpha_j = $0,0, pokud je zadána méně než $2 ^ n $.