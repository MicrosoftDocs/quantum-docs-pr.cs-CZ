---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliGenIdx_
title: _PQTermToPauliGenIdx_ – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 7f1794f9e46323ccf722407fb7ae82f73ed76e40
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215431"
---
# <a name="_pqtermtopauligenidx_-function"></a>_PQTermToPauliGenIdx_ – funkce

Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Převede GeneratorIndex s popisem výrazu PQ na výraz GeneratorIndex [] v souvislosti s Paul.

```qsharp
function _PQTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a>Vstup

### <a name="term--generatorindex"></a>termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` představuje PQ termín.



## <a name="output--generatorindex"></a>Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]

"GeneratorIndex []" vyjadřující PQ termín jako Pauli podmínky.