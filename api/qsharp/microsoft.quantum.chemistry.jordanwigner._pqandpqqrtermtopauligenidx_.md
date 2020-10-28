---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliGenIdx_
title: _PQandPQQRTermToPauliGenIdx_ – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 44a6d6b63d2f6bc8b628603e78931570d1ec22eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698552"
---
# <a name="_pqandpqqrtermtopauligenidx_-function"></a><span data-ttu-id="e51cd-102">_PQandPQQRTermToPauliGenIdx_ – funkce</span><span class="sxs-lookup"><span data-stu-id="e51cd-102">_PQandPQQRTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="e51cd-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="e51cd-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="e51cd-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e51cd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e51cd-105">Převede GeneratorIndex s popisem podmínky PQ nebo PQQR na výraz GeneratorIndex [] v souvislosti s Paul.</span><span class="sxs-lookup"><span data-stu-id="e51cd-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="e51cd-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e51cd-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="e51cd-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e51cd-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e51cd-108">`GeneratorIndex` představuje termín PQ nebo PQQR.</span><span class="sxs-lookup"><span data-stu-id="e51cd-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="e51cd-109">Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="e51cd-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="e51cd-110">"GeneratorIndex []" vyjadřující PQ nebo PQQR Term jako podmínky pro Pauli.</span><span class="sxs-lookup"><span data-stu-id="e51cd-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>