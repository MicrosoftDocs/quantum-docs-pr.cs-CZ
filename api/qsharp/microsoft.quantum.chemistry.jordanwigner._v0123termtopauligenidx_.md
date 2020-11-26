---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: _V0123TermToPauliGenIdx_ – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: fc5ad0e97374c52a90012b0ce633af8488f3ad88
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215091"
---
# <a name="_v0123termtopauligenidx_-function"></a>_V0123TermToPauliGenIdx_ – funkce

Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Převede GeneratorIndex s popisem výrazu PQRS na výraz GeneratorIndex [] v souvislosti s Paul.

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a>Vstup

### <a name="term--generatorindex"></a>termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` představuje PQRS termín.



## <a name="output--generatorindex"></a>Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]

"GeneratorIndex []" vyjadřující PQRS termín jako Pauli podmínky.