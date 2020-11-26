---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: 2dd3c705b0496df1719dc677e4defea5e435b839
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229286"
---
# <a name="identitygeneratorindex-function"></a>IdentityGeneratorIndex – funkce

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí index generátoru konzistentní s nulovým Hamiltonian, `H = 0` který odpovídá operaci vývoje identity.

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Vstup

### <a name="idxterm--int"></a>idxTerm: [int](xref:microsoft.quantum.lang-ref.int)

Tento vstup je ignorován a je definován pro konzistenci s <xref:microsoft.quantum.simulation.generatorsystem> uživatelem definovaným typem.



## <a name="output--generatorindex"></a>Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Index generátoru představující vývoj pod Hamiltonian $H = $0.