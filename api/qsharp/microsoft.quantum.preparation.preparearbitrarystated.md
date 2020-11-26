---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryStateD
title: Operace PrepareArbitraryStateD
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryStateD
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: cca0ea16dca3f3da8ce76a43f1012ffa0e4a72e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210603"
---
# <a name="preparearbitrarystated-operation"></a>Operace PrepareArbitraryStateD

Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vzhledem k sadě koeficientů a registru s kódováním nenaloženého formátu Little endian připraví stav v tomto registru, který je popsán v daných koeficientech.

```qsharp
operation PrepareArbitraryStateD (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Tato operace připraví libovolný stav pro každý kraj $ \ket{\psi} $ pomocí složitých koeficientů $r _j e ^ {i t_j} $ ze stavu $n $-qubit výpočetního základu $ \ket{0 \cdots 0} $.
Konkrétně lze akci této operace simulovat pomocí jednotkové transformace $U $, která funguje se stavem vše-nuly jako

$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.
\end{align} $ $

## <a name="input"></a>Vstup

### <a name="coefficients--double"></a>koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]

Pole až do $2 ^ n $ reálných koeficientů. $J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit registruje číselné kódování stavů ve formátu Little endian. Očekává se, že se má inicializovat ve stavu výpočtu $ \ket{0...0} $.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Negativní vstupní koeficienty $r _j < $0 budou považovány za kladné s hodnotou $ | r_j | $. `coefficients` bude doplněna elementy $ (r_j, t_j) = (0,0, 0,0) $, pokud je zadáno méně než $2 ^ n $.

## <a name="references"></a>Reference

- Shrnutí logických okruhů Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Viz také

- [Microsoft. Přípravno. Preparation. ApproximatelyPrepareArbitraryState](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)