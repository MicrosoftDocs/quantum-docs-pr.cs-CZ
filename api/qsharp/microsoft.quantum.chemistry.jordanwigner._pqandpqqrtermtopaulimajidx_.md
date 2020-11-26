---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliMajIdx_
title: _PQandPQQRTermToPauliMajIdx_ – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 1a04f5f3b66e0dccb650b2d451a086a380b9810a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225002"
---
# <a name="_pqandpqqrtermtopaulimajidx_-function"></a><span data-ttu-id="2d55d-102">_PQandPQQRTermToPauliMajIdx_ – funkce</span><span class="sxs-lookup"><span data-stu-id="2d55d-102">_PQandPQQRTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="2d55d-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="2d55d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="2d55d-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="2d55d-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="2d55d-105">Převede GeneratorIndex s popisem podmínky PQ nebo PQQR na výraz GeneratorIndex [] v souvislosti s Paul.</span><span class="sxs-lookup"><span data-stu-id="2d55d-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="2d55d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2d55d-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="2d55d-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="2d55d-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="2d55d-108">`GeneratorIndex` představuje termín PQ nebo PQQR.</span><span class="sxs-lookup"><span data-stu-id="2d55d-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="2d55d-109">Výstup: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="2d55d-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="2d55d-110">"GeneratorIndex []" vyjadřující PQ nebo PQQR Term jako podmínky pro Pauli.</span><span class="sxs-lookup"><span data-stu-id="2d55d-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>