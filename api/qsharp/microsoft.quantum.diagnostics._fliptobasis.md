---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: operace _flipToBasis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: e074ed2ae259f6aef49a8d327ce518a9e2caebfa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698201"
---
# <a name="_fliptobasis-operation"></a><span data-ttu-id="e3a5c-102">operace _flipToBasis</span><span class="sxs-lookup"><span data-stu-id="e3a5c-102">_flipToBasis operation</span></span>

<span data-ttu-id="e3a5c-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e3a5c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e3a5c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e3a5c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e3a5c-105">Aplikuje unitaries, které map $ \ket {0} \otimes\cdots\ket {0} $ to $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $, kde $ \ket{\ psi_k} $ závisí na `basis[k]` .</span><span class="sxs-lookup"><span data-stu-id="e3a5c-105">Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.</span></span>

<span data-ttu-id="e3a5c-106">Korespondence mezi hodnotou `basis[k]` a $ \ket{\ psi_k} $ je následující:</span><span class="sxs-lookup"><span data-stu-id="e3a5c-106">The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:</span></span>

- <span data-ttu-id="e3a5c-107">`basis[k]=0` $ \rightarrow \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="e3a5c-107">`basis[k]=0` $\rightarrow \ket{0}$.</span></span>
- <span data-ttu-id="e3a5c-108">`basis[k]=1` $ \rightarrow \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="e3a5c-108">`basis[k]=1` $\rightarrow \ket{1}$.</span></span>
- <span data-ttu-id="e3a5c-109">`basis[k]=2` $ \rightarrow \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="e3a5c-109">`basis[k]=2` $\rightarrow \ket{+}$.</span></span>
- <span data-ttu-id="e3a5c-110">`basis[k]=3` $ \rightarrow \ket{i} $ (+ 1 eigenstate Pauli Y).</span><span class="sxs-lookup"><span data-stu-id="e3a5c-110">`basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).</span></span>

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e3a5c-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="e3a5c-111">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="e3a5c-112">Základna: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e3a5c-112">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e3a5c-113">Pole ID stavu s jednou qubit (0 <= ID <= 3), jedna pro každý prvek qubits.</span><span class="sxs-lookup"><span data-stu-id="e3a5c-113">Array of single-qubit basis state IDs (0 <= id <= 3), one for each element of qubits.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="e3a5c-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e3a5c-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e3a5c-115">Qubit, na kterém má být provozován.</span><span class="sxs-lookup"><span data-stu-id="e3a5c-115">Qubit to be operated on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e3a5c-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e3a5c-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

