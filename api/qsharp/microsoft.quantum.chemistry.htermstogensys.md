---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 936e1bcc58b2f1af3bdb606884128c38d2f58867
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204109"
---
# <a name="htermstogensys-function"></a>HTermsToGenSys – funkce

Obor názvů: [Microsoft.. chemie](xref:Microsoft.Quantum.Chemistry)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Převede Hamiltonian ve `HTerm[]` formátu dat na GeneratorSystem.

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Vstup

### <a name="data--hterm"></a>data: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

Vstupní data ve `HTerm[]` formátu.


### <a name="termtype--int"></a>termType: [int](xref:microsoft.quantum.lang-ref.int)[]

Další informace přidané do GeneratorIndex



## <a name="output--generatorsystem"></a>Výstup: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

GeneratorSystem představující Hamiltonian reprezentovaný vstupem `data` .