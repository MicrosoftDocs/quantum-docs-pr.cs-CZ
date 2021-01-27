---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Operace exp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 7aa6974e83e917125b63ef91fb5c3b1238f6e856
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819014"
---
# <a name="exp-operation"></a><span data-ttu-id="81f47-102">Operace exp</span><span class="sxs-lookup"><span data-stu-id="81f47-102">Exp operation</span></span>

<span data-ttu-id="81f47-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="81f47-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="81f47-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="81f47-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="81f47-105">Aplikuje exponenciální hodnotu qubit operátoru Pauli.</span><span class="sxs-lookup"><span data-stu-id="81f47-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="81f47-106">\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}, \end{align}, kde $P _i $ je prvek $i $ th `paulis` a kde $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="81f47-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="81f47-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="81f47-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="81f47-108">Pauls: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="81f47-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="81f47-109">Pole hodnot qubit Pauli, které označují faktory tensor produktů na každé qubit.</span><span class="sxs-lookup"><span data-stu-id="81f47-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="81f47-110">théta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="81f47-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="81f47-111">Úhel o daném qubit operátoru Pauli, pomocí kterého se má cílový registr otočit</span><span class="sxs-lookup"><span data-stu-id="81f47-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="81f47-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="81f47-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="81f47-113">Zaregistrujte se na použití daného otočení na.</span><span class="sxs-lookup"><span data-stu-id="81f47-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="81f47-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81f47-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

