---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliGenIdx
title: _ZTermToPauliGenIdx funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 4e08ef7f5033b22cb69e77936f83229cbd85aa64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839105"
---
# <a name="_ztermtopauligenidx-function"></a><span data-ttu-id="bc8a9-102">_ZTermToPauliGenIdx funkce</span><span class="sxs-lookup"><span data-stu-id="bc8a9-102">_ZTermToPauliGenIdx function</span></span>

<span data-ttu-id="bc8a9-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="bc8a9-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="bc8a9-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="bc8a9-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="bc8a9-105">Převede GeneratorIndex popisující termín Z na výraz "GeneratorIndex []" v souvislosti s Paul.</span><span class="sxs-lookup"><span data-stu-id="bc8a9-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="bc8a9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="bc8a9-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="bc8a9-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="bc8a9-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="bc8a9-108">`GeneratorIndex` představuje termín Z.</span><span class="sxs-lookup"><span data-stu-id="bc8a9-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="bc8a9-109">Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="bc8a9-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="bc8a9-110">"GeneratorIndex []" vyjadřuje termíny Z termínu Pauli.</span><span class="sxs-lookup"><span data-stu-id="bc8a9-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>