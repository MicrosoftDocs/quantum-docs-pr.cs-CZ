---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerClusterOperatorGeneratorSystem
title: JordanWignerClusterOperatorGeneratorSystem – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerClusterOperatorGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: e6deca3c8261c7730e9b208d9f834ad0db101fd3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214802"
---
# <a name="jordanwignerclusteroperatorgeneratorsystem-function"></a>JordanWignerClusterOperatorGeneratorSystem – funkce

Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Převede Hamiltonian, který popisuje, `JWOptimizedHTerms` na `GeneratorSystem` vyjádřené v `GeneratorIndex` konvenci definované v tomto souboru.

```qsharp
function JordanWignerClusterOperatorGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Vstup

### <a name="data--jordanwignerinputstate"></a>data: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]

Popis Hamiltonian ve `JWOptimizedHTerms` formátu



## <a name="output--generatorsystem"></a>Výstup: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Reprezentace Hamiltonian jako `GeneratorSystem` .