---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 7b93a6674bec974e61496696a3d8403225b16d80
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225597"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a>_IdentityTimeDependentGeneratorSystem funkce

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí systém generátoru konzistentní s Hamiltonian `H(s) = 0` , kde `s` je parametr plánu.

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Vstup

### <a name="schedule--double"></a>Schedule: [Double](xref:microsoft.quantum.lang-ref.double)

Tento vstup je ignorován a je definován pro konzistenci s <xref:microsoft.quantum.canon.timedependentgeneratorsystem> uživatelem definovaným typem.



## <a name="output--generatorsystem"></a>Výstup: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Systém generátoru, který představuje vývoj v rámci Hamiltonian $H (s) = $0 pro všechny $s $.