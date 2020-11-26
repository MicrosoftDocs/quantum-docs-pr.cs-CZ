---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionEvolutionSet
title: JordanWignerFermionEvolutionSet – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 31218f88d1446c232290ac7695c1ae01efbe22ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224985"
---
# <a name="jordanwignerfermionevolutionset-function"></a><span data-ttu-id="1b495-102">JordanWignerFermionEvolutionSet – funkce</span><span class="sxs-lookup"><span data-stu-id="1b495-102">JordanWignerFermionEvolutionSet function</span></span>

<span data-ttu-id="1b495-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="1b495-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="1b495-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="1b495-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="1b495-105">Představuje dynamický generátor jako sadu simulovaných bran a rozšíření v JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="1b495-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function JordanWignerFermionEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a><span data-ttu-id="1b495-106">Výstup: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="1b495-106">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="1b495-107">Objekt `EvolutionSet` , který mapuje `GeneratorIndex` pro JordanWigner na EvolutionUnitary.</span><span class="sxs-lookup"><span data-stu-id="1b495-107">An `EvolutionSet` that maps a `GeneratorIndex` for the JordanWigner basis to an \`EvolutionUnitary.</span></span>