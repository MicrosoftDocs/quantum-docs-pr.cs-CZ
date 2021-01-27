---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: Operace ExpFrac
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 6634caff164c841876fb53e79c3f93254a7d624c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849423"
---
# <a name="expfrac-operation"></a><span data-ttu-id="a377a-102">Operace ExpFrac</span><span class="sxs-lookup"><span data-stu-id="a377a-102">ExpFrac operation</span></span>

<span data-ttu-id="a377a-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="a377a-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="a377a-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a377a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a377a-105">Aplikuje exponenciální operátor qubit Pauli s argumentem daným zlomkem dyadic.</span><span class="sxs-lookup"><span data-stu-id="a377a-105">Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.</span></span>

<span data-ttu-id="a377a-106">\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align} kde $P _i $ je prvek $i $ th `paulis` a kde $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="a377a-106">\begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a377a-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="a377a-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="a377a-108">Pauls: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="a377a-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="a377a-109">Pole hodnot qubit Pauli, které označují faktory tensor produktů na každé qubit.</span><span class="sxs-lookup"><span data-stu-id="a377a-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="a377a-110">Čitatel: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a377a-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a377a-111">Čitatel ($k $) ve zlomku dyadic zlomku úhlu, podle kterého se má otočit registr qubit.</span><span class="sxs-lookup"><span data-stu-id="a377a-111">Numerator ($k$) in the dyadic fraction representation of the angle by which the qubit register is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="a377a-112">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a377a-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a377a-113">Mocnina dvou ($n $) určující jmenovatele úhlu, podle kterého se má otočit registr qubit.</span><span class="sxs-lookup"><span data-stu-id="a377a-113">Power of two ($n$) specifying the denominator of the angle by which the qubit register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a377a-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a377a-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a377a-115">Zaregistrujte se na použití daného otočení na.</span><span class="sxs-lookup"><span data-stu-id="a377a-115">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a377a-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a377a-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

