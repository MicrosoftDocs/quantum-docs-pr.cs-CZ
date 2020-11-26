---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: Operace ApplyOuterCDKMAdder
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: 81311a75beedb62331184faf4e1523f3ccc74f43
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190662"
---
# <a name="applyoutercdkmadder-operation"></a>Operace ApplyOuterCDKMAdder

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vratný, místní Ripple – operace, která se používá v operaci sčítání celého čísla RippleCarryAdderCDKM níže.
Vzhledem k dvěma registrům qubit `xs` a `ys` stejné délce operace použije Ripple sekvenci pro CNOT a CCNOT brány s qubits v `xs` a `ys` jako ovládací prvky a qubits v `xs` jako cíle.

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

První qubit registr obsahující ovládací prvky a cíle.


### <a name="ys--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Druhý qubit registr přispívá k ovládacím prvkům.


### <a name="ancilla--qubit"></a>ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Do této operace byla předána ancilla qubit použitá v RippleCarryAdderCDKM.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Reference

- Steven A. Cuccaro, Tomáš G. Draper, Samuel A. Kutin, David Petrie Moulton: "nové v rámci Ripple – přenést okruh", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1