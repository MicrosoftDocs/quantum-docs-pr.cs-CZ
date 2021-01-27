---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: InterpolateGeneratorSystemsImpl – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: a902a93968d221349f9a6fa977bbc1706971fcfd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855754"
---
# <a name="interpolategeneratorsystemsimpl-function"></a>InterpolateGeneratorSystemsImpl – funkce

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Lineárně interpoluje dvě `GeneratorSystems` závislosti na parametru plánu `s` mezi 0 a 1 (včetně).

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Vstup

### <a name="schedule--double"></a>Schedule: [Double](xref:microsoft.quantum.lang-ref.double)

Parametr plánu $s \in [0, 1] $.


### <a name="generatorsystemstart--generatorsystem"></a>generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Spustí se `GeneratorSystem` .


### <a name="generatorsystemend--generatorsystem"></a>generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Konec `GeneratorSystem` .



## <a name="output--generatorsystem"></a>Výstup: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`Představuje systém, který je součtem systémů generátorů vstupu, s váhou $ (1-s) $ zapnutou `generatorSystemStart` a váhou $s $ on `generatorSystemEnd` .

## <a name="see-also"></a>Viz také

- [Microsoft. v. simulace. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)