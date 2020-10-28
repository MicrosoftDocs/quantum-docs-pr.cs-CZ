---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 89c81aca4cfad6087d764ac8f5a0f1426e905e4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707815"
---
# <a name="paulievolutionset-function"></a>PauliEvolutionSet – funkce

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček [](https://nuget.org/packages/)


Představuje dynamický generátor jako sadu simulovaných bran a rozšíření v Pauli.

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a>Výstup: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

Objekt `EvolutionSet` , který mapuje `GeneratorIndex` pro Pauli na EvolutionUnitary.

## <a name="remarks"></a>Poznámky

Tato třída je získána částečnou aplikací <xref:microsoft.quantum.simulation.paulievolutionfunction> .