---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationComplexCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 1d0efa7b83d2e8e75c4b293866f3929f357ec44b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210365"
---
# <a name="statepreparationcomplexcoefficients-function"></a>StatePreparationComplexCoefficients – funkce

Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> StatePreparationComplexCoefficients se už nepoužívá. <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP>Místo toho ho použijte.

Vrátí operaci, která připraví určitý stav nečinnosti.

Vrácená operace $U $ připraví libovolný stav za běhu $ \ket{\psi} $ pomocí složitých koeficientů $r _j e ^ {i t_j} $ ze stavu výpočtu $n $-qubit výpočetního základu $ \ket{0...0} $.

Akce U nově přiděleného registru je dána $ $ \begin{align} U\ket {0... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.
\end{align} $ $

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Vstup

### <a name="coefficients--complexpolar"></a>koeficienty: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

Pole až do $2 ^ n $ složitých koeficientů reprezentovaných jejich absolutní hodnotou a fází $ (r_j, t_j) $. $J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.



## <a name="output--littleendian--unit--is-adj--ctl"></a>Výstup: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je ADJ + CTL

Jednotná provozní operace pro přípravu stavu $U $.

## <a name="remarks"></a>Poznámky

Negativní vstupní koeficienty $r _j < $0 budou považovány za kladné s hodnotou $ | r_j | $. `coefficients` bude doplněna elementy $ (r_j, t_j) = (0,0, 0,0) $, pokud je zadáno méně než $2 ^ n $.