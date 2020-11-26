---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerGeneratorSystem
title: JordanWignerGeneratorSystem – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 0f6719cfac1c50cd55da30e57b0b5c5214813f24
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214717"
---
# <a name="jordanwignergeneratorsystem-function"></a>JordanWignerGeneratorSystem – funkce

Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Převede Hamiltonian, který popisuje, `JWOptimizedHTerms` na `GeneratorSystem` vyjádřené v `GeneratorIndex` konvenci definované v tomto souboru.

```qsharp
function JordanWignerGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Vstup

### <a name="data--jwoptimizedhterms"></a>data: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)

Popis Hamiltonian ve `JWOptimizedHTerms` formátu



## <a name="output--generatorsystem"></a>Výstup: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Reprezentace Hamiltonian jako `GeneratorSystem` .