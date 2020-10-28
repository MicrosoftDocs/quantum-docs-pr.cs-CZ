---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Operace exp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: b923374a954f90aba2deaead79dd419fbf67fea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697737"
---
# <a name="exp-operation"></a><span data-ttu-id="80d2a-102">Operace exp</span><span class="sxs-lookup"><span data-stu-id="80d2a-102">Exp operation</span></span>

<span data-ttu-id="80d2a-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="80d2a-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="80d2a-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="80d2a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="80d2a-105">Aplikuje exponenciální hodnotu qubit operátoru Pauli.</span><span class="sxs-lookup"><span data-stu-id="80d2a-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="80d2a-106">\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}, \end{align}, kde $P _i $ je prvek $i $ th `paulis` a kde $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="80d2a-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="80d2a-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="80d2a-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="80d2a-108">Pauls: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="80d2a-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="80d2a-109">Pole hodnot qubit Pauli, které označují faktory tensor produktů na každé qubit.</span><span class="sxs-lookup"><span data-stu-id="80d2a-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="80d2a-110">théta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="80d2a-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="80d2a-111">Úhel o daném qubit operátoru Pauli, pomocí kterého se má cílový registr otočit</span><span class="sxs-lookup"><span data-stu-id="80d2a-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="80d2a-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="80d2a-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="80d2a-113">Zaregistrujte se na použití daného otočení na.</span><span class="sxs-lookup"><span data-stu-id="80d2a-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="80d2a-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80d2a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

