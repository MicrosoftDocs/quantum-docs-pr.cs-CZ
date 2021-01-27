---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 6904054bb1aff3a57c80882694b4c217812b2b81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842225"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="908f5-102">IntsToPaulis – funkce</span><span class="sxs-lookup"><span data-stu-id="908f5-102">IntsToPaulis function</span></span>

<span data-ttu-id="908f5-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="908f5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="908f5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="908f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="908f5-105">Převede pole celých čísel na pole qubitch operátorů Pauli s jedním.</span><span class="sxs-lookup"><span data-stu-id="908f5-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="908f5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="908f5-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="908f5-107">čísla: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="908f5-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="908f5-108">Pole celých čísel v rozsahu `0..3`  , který má být převeden na Pauli operátory.</span><span class="sxs-lookup"><span data-stu-id="908f5-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="908f5-109">Výstup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="908f5-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="908f5-110">Pole `paulis` operátorů Pauli `Pauli[]` se stejnou délkou `ints` , která `paulis[idxPauli]` je rovna elementu z `[PauliI, PauliX, PauliY, PauliZ]` daného `ints[idxPauli]` .</span><span class="sxs-lookup"><span data-stu-id="908f5-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>