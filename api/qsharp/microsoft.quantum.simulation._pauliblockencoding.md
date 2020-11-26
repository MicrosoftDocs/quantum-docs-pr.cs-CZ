---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: _PauliBlockEncoding funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 6ad3e692f68ec2d405e19a7e467ef8fe33d449fc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225563"
---
# <a name="_pauliblockencoding-function"></a>_PauliBlockEncoding funkce

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vytvoří jednotkové kódování bloku pro Hamiltonian.

Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ je popsána na základě součtu Pauli podmínek $P _j $, každý s reálným koeficientem $ \ alpha_j $.

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Vstup

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

A `GeneratorSystem` který popisuje $H $ jako součet podmínek Pauli


### <a name="stateprepunitary--double---littleendian--unit--is-adj--ctl"></a>statePrepUnitary: [Double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Jednotková operace $V $, která používá jednotkovou $V _j $ řízenou v indexu $ \ket{j} $, a to s ohledem na funkci $f: j\rightarrow V_j $.


### <a name="multiplexer--intint---qubit--unit--is-adj--ctl---littleendianqubit--unit--is-adj--ctl"></a>multiplexor: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL)-> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL.





## <a name="output--doubleblockencodingreflection"></a>Výstup: ([Double](xref:microsoft.quantum.lang-ref.double);[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>První parametr

Jedna-norma koeficientů $ \Alpha = \ sum_ {j} | \ alpha_j | $

## <a name="second-parameter"></a>Druhý parametr

`BlockEncodingReflection`Jednotková $U $ $U Hamiltonian $. Protože tato jednotná operace splňuje $U ^ 2 = I $, je také odraz.

## <a name="remarks"></a>Poznámky

Příklady operací, které připravují a odstavují stav $ \ sum_ {j}, alpha_j/\Alpha}\ket{j} $, a vytvoří jednotkovou jednotně řízenou hodnotou <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> a <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .