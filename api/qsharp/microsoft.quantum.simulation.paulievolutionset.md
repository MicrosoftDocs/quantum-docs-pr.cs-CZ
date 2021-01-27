---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 961c95e6787b69e35ca531fa36164cc988ad660d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847964"
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