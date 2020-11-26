---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Operace měření
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: 804ae72ed2d5302b14011b737b7ed3ad2b9a14ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212286"
---
# <a name="measure-operation"></a><span data-ttu-id="4ee6a-102">Operace měření</span><span class="sxs-lookup"><span data-stu-id="4ee6a-102">Measure operation</span></span>

<span data-ttu-id="4ee6a-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="4ee6a-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="4ee6a-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4ee6a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4ee6a-105">Provede společné měření jednoho nebo více qubits v zadaných základech Pauli.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-105">Performs a joint measurement of one or more qubits in the specified Pauli bases.</span></span>

<span data-ttu-id="4ee6a-106">Výsledek výstupu je dán distribucí: \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \frac12 \braket{\psi \mid | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \psi}, \end{align} kde $P _i $ je $i $ th prvek `bases` a kde $N = \texttt{Length} (\texttt{Bases}) $.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-106">The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$.</span></span>
<span data-ttu-id="4ee6a-107">To znamená, že měření vrátí `Result` $d $ tak, že eigenvalue účinek pozorovaného měření je $ (-1) ^ d $.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-107">That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.</span></span>

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="4ee6a-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="4ee6a-108">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="4ee6a-109">základ: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="4ee6a-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="4ee6a-110">Pole hodnot qubit Pauli, které označují faktory tensor produktů na každé qubit.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-110">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="4ee6a-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4ee6a-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4ee6a-112">Registrace qubits, která se má měřit</span><span class="sxs-lookup"><span data-stu-id="4ee6a-112">Register of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="4ee6a-113">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="4ee6a-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="4ee6a-114">`Zero` Pokud se eigenvalue $ + $1, a `One` Pokud je zjištěna $-$1 eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-114">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ee6a-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4ee6a-115">Remarks</span></span>

<span data-ttu-id="4ee6a-116">Pokud jsou pole základu a qubit různými délkami, operace se nezdaří.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-116">If the basis array and qubit array are different lengths, then the operation will fail.</span></span>