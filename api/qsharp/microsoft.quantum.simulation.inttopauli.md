---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229201"
---
# <a name="inttopauli-function"></a><span data-ttu-id="98f25-102">IntToPauli – funkce</span><span class="sxs-lookup"><span data-stu-id="98f25-102">IntToPauli function</span></span>

<span data-ttu-id="98f25-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="98f25-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="98f25-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="98f25-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="98f25-105">Převede celé číslo na operátor Pauli s jedním qubit.</span><span class="sxs-lookup"><span data-stu-id="98f25-105">Converts a integer to a single-qubit Pauli operator.</span></span>

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a><span data-ttu-id="98f25-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="98f25-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="98f25-107">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="98f25-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="98f25-108">Celé číslo v rozsahu `0..3` , které má být převedeno na Pauli operátory.</span><span class="sxs-lookup"><span data-stu-id="98f25-108">Integer in the range `0..3` to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="98f25-109">Výstup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="98f25-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="98f25-110">`Pauli`Operátor daného `[PauliI, PauliX, PauliY, PauliZ][idx]` .</span><span class="sxs-lookup"><span data-stu-id="98f25-110">A `Pauli` operator given by `[PauliI, PauliX, PauliY, PauliZ][idx]`.</span></span>