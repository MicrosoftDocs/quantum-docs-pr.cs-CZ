---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: operace _flipToBasis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: d46c42846066befafda2af22f7b6e861cb260c33
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831013"
---
# <a name="_fliptobasis-operation"></a><span data-ttu-id="fa1a4-102">operace _flipToBasis</span><span class="sxs-lookup"><span data-stu-id="fa1a4-102">_flipToBasis operation</span></span>

<span data-ttu-id="fa1a4-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="fa1a4-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="fa1a4-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="fa1a4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fa1a4-105">Aplikuje unitaries, které map $ \ket {0} \otimes\cdots\ket {0} $ to $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $, kde $ \ket{\ psi_k} $ závisí na `basis[k]` .</span><span class="sxs-lookup"><span data-stu-id="fa1a4-105">Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.</span></span>

<span data-ttu-id="fa1a4-106">Korespondence mezi hodnotou `basis[k]` a $ \ket{\ psi_k} $ je následující:</span><span class="sxs-lookup"><span data-stu-id="fa1a4-106">The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:</span></span>

- <span data-ttu-id="fa1a4-107">`basis[k]=0` $ \rightarrow \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="fa1a4-107">`basis[k]=0` $\rightarrow \ket{0}$.</span></span>
- <span data-ttu-id="fa1a4-108">`basis[k]=1` $ \rightarrow \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="fa1a4-108">`basis[k]=1` $\rightarrow \ket{1}$.</span></span>
- <span data-ttu-id="fa1a4-109">`basis[k]=2` $ \rightarrow \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="fa1a4-109">`basis[k]=2` $\rightarrow \ket{+}$.</span></span>
- <span data-ttu-id="fa1a4-110">`basis[k]=3` $ \rightarrow \ket{i} $ (+ 1 eigenstate Pauli Y).</span><span class="sxs-lookup"><span data-stu-id="fa1a4-110">`basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).</span></span>

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fa1a4-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="fa1a4-111">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="fa1a4-112">Základna: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fa1a4-112">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fa1a4-113">Pole ID stavu s jednou qubit (0 <= ID <= 3), jedna pro každý prvek qubits.</span><span class="sxs-lookup"><span data-stu-id="fa1a4-113">Array of single-qubit basis state IDs (0 <= id <= 3), one for each element of qubits.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="fa1a4-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fa1a4-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fa1a4-115">Qubit, na kterém má být provozován.</span><span class="sxs-lookup"><span data-stu-id="fa1a4-115">Qubit to be operated on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fa1a4-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fa1a4-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

