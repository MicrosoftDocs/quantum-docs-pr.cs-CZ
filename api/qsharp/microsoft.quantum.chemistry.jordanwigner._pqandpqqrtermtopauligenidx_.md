---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliGenIdx_
title: _PQandPQQRTermToPauliGenIdx_ – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: c4de9593927b12b2387ae0b46513970308f59c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839330"
---
# <a name="_pqandpqqrtermtopauligenidx_-function"></a><span data-ttu-id="ef1c9-102">_PQandPQQRTermToPauliGenIdx_ – funkce</span><span class="sxs-lookup"><span data-stu-id="ef1c9-102">_PQandPQQRTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="ef1c9-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="ef1c9-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="ef1c9-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="ef1c9-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="ef1c9-105">Převede GeneratorIndex s popisem podmínky PQ nebo PQQR na výraz GeneratorIndex [] v souvislosti s Paul.</span><span class="sxs-lookup"><span data-stu-id="ef1c9-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="ef1c9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ef1c9-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="ef1c9-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="ef1c9-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="ef1c9-108">`GeneratorIndex` představuje termín PQ nebo PQQR.</span><span class="sxs-lookup"><span data-stu-id="ef1c9-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="ef1c9-109">Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="ef1c9-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="ef1c9-110">"GeneratorIndex []" vyjadřující PQ nebo PQQR Term jako podmínky pro Pauli.</span><span class="sxs-lookup"><span data-stu-id="ef1c9-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>