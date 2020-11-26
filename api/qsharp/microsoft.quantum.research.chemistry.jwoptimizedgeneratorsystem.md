---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedGeneratorSystem
title: JWOptimizedGeneratorSystem – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 321b58ba4a458ad53579d2480258a92ba48de169
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225699"
---
# <a name="jwoptimizedgeneratorsystem-function"></a><span data-ttu-id="79faf-102">JWOptimizedGeneratorSystem – funkce</span><span class="sxs-lookup"><span data-stu-id="79faf-102">JWOptimizedGeneratorSystem function</span></span>

<span data-ttu-id="79faf-103">Obor názvů: [Microsoft. Prohledávejte. Research. chemie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="79faf-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="79faf-104">Balíček: [Microsoft. prostudoval. Research. chemie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="79faf-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="79faf-105">Převede Hamiltonian, který popisuje, `JWOptimizedHTerms` na `GeneratorSystem` vyjádřené v `GeneratorIndex` konvenci definované v tomto souboru.</span><span class="sxs-lookup"><span data-stu-id="79faf-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JWOptimizedGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="79faf-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="79faf-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="79faf-107">data: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="79faf-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="79faf-108">Popis Hamiltonian ve `JWOptimizedHTerms` formátu</span><span class="sxs-lookup"><span data-stu-id="79faf-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="79faf-109">Výstup: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="79faf-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="79faf-110">Reprezentace Hamiltonian jako `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="79faf-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>