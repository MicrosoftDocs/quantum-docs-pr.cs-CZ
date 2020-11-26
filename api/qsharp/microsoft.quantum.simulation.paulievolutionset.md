---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: fb53b90b6ab5ce1003f66b68a8c2ad8b3631f627
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230341"
---
# <a name="paulievolutionset-function"></a>PauliEvolutionSet – funkce

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje dynamický generátor jako sadu simulovaných bran a rozšíření v Pauli.

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a>Výstup: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

Objekt `EvolutionSet` , který mapuje `GeneratorIndex` pro Pauli na EvolutionUnitary.

## <a name="remarks"></a>Poznámky

Tato třída je získána částečnou aplikací <xref:microsoft.quantum.simulation.paulievolutionfunction> .