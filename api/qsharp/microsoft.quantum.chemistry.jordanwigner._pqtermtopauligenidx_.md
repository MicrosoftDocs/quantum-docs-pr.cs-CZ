---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliGenIdx_
title: _PQTermToPauliGenIdx_ – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 046b3b7b78cee7f046607277896100e20c33a32d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839311"
---
# <a name="_pqtermtopauligenidx_-function"></a><span data-ttu-id="cd8a7-102">_PQTermToPauliGenIdx_ – funkce</span><span class="sxs-lookup"><span data-stu-id="cd8a7-102">_PQTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="cd8a7-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="cd8a7-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="cd8a7-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="cd8a7-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="cd8a7-105">Převede GeneratorIndex s popisem výrazu PQ na výraz GeneratorIndex [] v souvislosti s Paul.</span><span class="sxs-lookup"><span data-stu-id="cd8a7-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="cd8a7-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="cd8a7-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="cd8a7-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="cd8a7-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="cd8a7-108">`GeneratorIndex` představuje PQ termín.</span><span class="sxs-lookup"><span data-stu-id="cd8a7-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="cd8a7-109">Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="cd8a7-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="cd8a7-110">"GeneratorIndex []" vyjadřující PQ termín jako Pauli podmínky.</span><span class="sxs-lookup"><span data-stu-id="cd8a7-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>