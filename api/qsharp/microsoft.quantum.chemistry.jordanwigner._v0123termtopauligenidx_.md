---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: _V0123TermToPauliGenIdx_ – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 8893d7c5479409a0ff98aa0b9e58f34fd3d274f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839196"
---
# <a name="_v0123termtopauligenidx_-function"></a><span data-ttu-id="7184d-102">_V0123TermToPauliGenIdx_ – funkce</span><span class="sxs-lookup"><span data-stu-id="7184d-102">_V0123TermToPauliGenIdx_ function</span></span>

<span data-ttu-id="7184d-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="7184d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="7184d-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7184d-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="7184d-105">Převede GeneratorIndex s popisem výrazu PQRS na výraz GeneratorIndex [] v souvislosti s Paul.</span><span class="sxs-lookup"><span data-stu-id="7184d-105">Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="7184d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="7184d-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="7184d-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="7184d-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="7184d-108">`GeneratorIndex` představuje PQRS termín.</span><span class="sxs-lookup"><span data-stu-id="7184d-108">`GeneratorIndex` representing a PQRS term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="7184d-109">Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="7184d-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="7184d-110">"GeneratorIndex []" vyjadřující PQRS termín jako Pauli podmínky.</span><span class="sxs-lookup"><span data-stu-id="7184d-110">'GeneratorIndex[]' expressing PQRS term as Pauli terms.</span></span>