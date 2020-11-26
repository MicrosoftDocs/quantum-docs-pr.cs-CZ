---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: a937dc648c5de5a5f6de7da996448af497b92185
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230306"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="05a87-102">PauliStringFromGenIdx – funkce</span><span class="sxs-lookup"><span data-stu-id="05a87-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="05a87-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="05a87-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="05a87-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="05a87-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="05a87-105">Extrahuje řetězec Pauli a jeho qubit indexy Pauliho výrazu, který je popsán v `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="05a87-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="05a87-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="05a87-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="05a87-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="05a87-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="05a87-108">`GeneratorIndex` typ, který zakóduje Pauli termín.</span><span class="sxs-lookup"><span data-stu-id="05a87-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="05a87-109">Výstup: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[];[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="05a87-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="05a87-110">Pauli řetězec termínu, který popisuje `GeneratorIndex` , a indexy pro qubits, na kterých působí.</span><span class="sxs-lookup"><span data-stu-id="05a87-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>