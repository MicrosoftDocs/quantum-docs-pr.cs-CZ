---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: Operace ApplyXControlledOnTruthTable
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: aa4e1bc0d5058228721728a894b896331ec626d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203293"
---
# <a name="applyxcontrolledontruthtable-operation"></a>Operace ApplyXControlledOnTruthTable

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje @"microsoft.quantum.intrinsic.x" operaci na `target` , pokud je logická funkce `func` vyhodnocena jako true pro klasické přiřazení v `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Operace implementuje jednotkovou operaci \begin{align} U\ket {x} \ KET {y} = \ket{x}\ket{y \oplus f (x)} \end{align}, kde $x $ a $y $ reprezentovat `controlRegister` a `target` v uvedeném pořadí.

Funkce Boolean $f $ je reprezentovaná jako tabulka pravdy v podobě velkých celých čísel.
Například funkce většina na třech vstupech je reprezentovaná BITSTRING `11101000` , kde nejvýznamnější bit `1` odpovídá vstupnímu přiřazení `(1, 1, 1)` , a nejméně významný bit `0` odpovídá vstupnímu přiřazení `(0, 0, 0)` .
Může být reprezentována velkým celým číslem `0xE8L` v šestnáctkovém zápisu nebo jako `232L` Desítkový zápis.  `L`Přípona označuje, že konstanta je typu `BigInt` .
Další podrobnosti o této prezentaci najdete také v tabulce [pravdy Kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).

Implementace využívá @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" brány a.

## <a name="input"></a>Vstup

### <a name="func--bigint"></a>Func: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Logická tabulka pravdy reprezentovaná jako velké celé číslo


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registrační qubits ovládacího prvku


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Cílový qubit



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Reference

- [*N. Schuch*, *J. Siewert*, PRL 91, no. 027902, 2003, arXiv: quant-pH/0303063](https://arxiv.org/abs/quant-ph/0303063)
- [*Mathias Soeken*, *Martin Roetteler*, arXiv: 2005.12310](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a>Viz také

- [Microsoft. proshrnutí. ApplyXControlledOnTruthTableWithCleanTarget](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)