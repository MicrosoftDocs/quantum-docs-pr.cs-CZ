---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: TruthTablesFromPermutationFolder – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 6b00c9e880ed7b7b3bf446dcb17dab3bab7a83a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708847"
---
# <a name="truthtablesfrompermutationfolder-function"></a><span data-ttu-id="1222b-102">TruthTablesFromPermutationFolder – funkce</span><span class="sxs-lookup"><span data-stu-id="1222b-102">TruthTablesFromPermutationFolder function</span></span>

<span data-ttu-id="1222b-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="1222b-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="1222b-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1222b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1222b-105">Logika rozkladu pro jeden index proměnné</span><span class="sxs-lookup"><span data-stu-id="1222b-105">Decomposition logic for a single variable index</span></span>

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a><span data-ttu-id="1222b-106">Popis</span><span class="sxs-lookup"><span data-stu-id="1222b-106">Description</span></span>

<span data-ttu-id="1222b-107">Tím se vezme aktuální stav, který vygeneruje aktualizovanou permutaci a případně přidá nové funkce pro řízené brány.</span><span class="sxs-lookup"><span data-stu-id="1222b-107">This takes the current state and generates an updated permutation and possibly adds new functions for controlled gates.</span></span>

## <a name="input"></a><span data-ttu-id="1222b-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="1222b-108">Input</span></span>

### <a name="numvars--int"></a><span data-ttu-id="1222b-109">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1222b-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="state--decompositionstate"></a><span data-ttu-id="1222b-110">stav: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="1222b-110">state : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>




### <a name="index--int"></a><span data-ttu-id="1222b-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1222b-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--decompositionstate"></a><span data-ttu-id="1222b-112">Výstup: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="1222b-112">Output : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>

