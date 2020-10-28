---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697145"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="60353-102">IntsToPaulis – funkce</span><span class="sxs-lookup"><span data-stu-id="60353-102">IntsToPaulis function</span></span>

<span data-ttu-id="60353-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="60353-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="60353-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="60353-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="60353-105">Převede pole celých čísel na pole qubitch operátorů Pauli s jedním.</span><span class="sxs-lookup"><span data-stu-id="60353-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="60353-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="60353-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="60353-107">čísla: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="60353-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="60353-108">Pole celých čísel v rozsahu `0..3`  , který má být převeden na Pauli operátory.</span><span class="sxs-lookup"><span data-stu-id="60353-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="60353-109">Výstup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="60353-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="60353-110">Pole `paulis` operátorů Pauli `Pauli[]` se stejnou délkou `ints` , která `paulis[idxPauli]` je rovna elementu z `[PauliI, PauliX, PauliY, PauliZ]` daného `ints[idxPauli]` .</span><span class="sxs-lookup"><span data-stu-id="60353-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>