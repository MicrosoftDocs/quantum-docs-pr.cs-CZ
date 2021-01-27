---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 2e37b40c60d19aa747114de988dddc19f0d7c50b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848005"
---
# <a name="pauliblockencoding-function"></a>PauliBlockEncoding – funkce

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vytvoří jednotkové kódování bloku pro Hamiltonian.

Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ je popsána na základě součtu Pauli podmínek $P _j $, každý s reálným koeficientem $ \ alpha_j $.

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Vstup

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

A `GeneratorSystem` který popisuje $H $ jako součet podmínek Pauli



## <a name="output--doubleblockencodingreflection"></a>Výstup: ([Double](xref:microsoft.quantum.lang-ref.double);[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>První parametr

Jedna-norma koeficientů $ \Alpha = \ sum_ {j} | \ alpha_j | $

## <a name="second-parameter"></a>Druhý parametr

`BlockEncodingReflection`Jednotková $U $ $H Hamiltonian $. Protože tato jednotná operace splňuje $U ^ 2 = I $, je také odraz.

## <a name="remarks"></a>Poznámky

To se získá tím, že se připraví a odpravují stav $ \ sum_ {j}, alpha_j/\Alpha}\ket{j} $ a vytvoří se jednotková a jednotně řízená s vynásobením <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .