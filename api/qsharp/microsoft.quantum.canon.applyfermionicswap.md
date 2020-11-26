---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Operace ApplyFermionicSWAP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 0c470705843a6360df0a72374570d86571397e41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218797"
---
# <a name="applyfermionicswap-operation"></a>Operace ApplyFermionicSWAP

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije prohození Fermionic.

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

V podstatě dojde k záměně qubits a při použití globální fáze-1, pokud obě qubits mají hodnotu 1. Zachová anti-symmetrization of orbitals.
Další informace naleznete v tématu .

Tato operace je reprezentována jednotkovým operátorem \begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}.
\end{align}

## <a name="input"></a>Vstup

### <a name="qubit1--qubit"></a>qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

První qubit, který se má vyměnit


### <a name="qubit2--qubit"></a>qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Druhý qubit, který se má prohodit.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Reference

- [*Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic kanál*, arXiv: 1706.00023](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a>Viz také

- [Microsoft.. vnitřní. SWAP](xref:Microsoft.Quantum.Intrinsic.SWAP)