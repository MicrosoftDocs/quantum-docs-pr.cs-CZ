---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Operace měření
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: 56ddfbe5e63692e477ad75bde6b1b16269ed20c0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697717"
---
# <a name="measure-operation"></a><span data-ttu-id="3c713-102">Operace měření</span><span class="sxs-lookup"><span data-stu-id="3c713-102">Measure operation</span></span>

<span data-ttu-id="3c713-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="3c713-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="3c713-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c713-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c713-105">Provede společné měření jednoho nebo více qubits v zadaných základech Pauli.</span><span class="sxs-lookup"><span data-stu-id="3c713-105">Performs a joint measurement of one or more qubits in the specified Pauli bases.</span></span>

<span data-ttu-id="3c713-106">Výsledek výstupu je dán distribucí: \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \frac12 \braket{\psi \mid | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \psi}, \end{align} kde $P _i $ je $i $ th prvek `bases` a kde $N = \texttt{Length} (\texttt{Bases}) $.</span><span class="sxs-lookup"><span data-stu-id="3c713-106">The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$.</span></span>
<span data-ttu-id="3c713-107">To znamená, že měření vrátí `Result` $d $ tak, že eigenvalue účinek pozorovaného měření je $ (-1) ^ d $.</span><span class="sxs-lookup"><span data-stu-id="3c713-107">That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.</span></span>

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="3c713-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="3c713-108">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="3c713-109">základ: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="3c713-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="3c713-110">Pole hodnot qubit Pauli, které označují faktory tensor produktů na každé qubit.</span><span class="sxs-lookup"><span data-stu-id="3c713-110">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="3c713-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3c713-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3c713-112">Registrace qubits, která se má měřit</span><span class="sxs-lookup"><span data-stu-id="3c713-112">Register of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="3c713-113">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="3c713-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="3c713-114">`Zero` Pokud se eigenvalue $ + $1, a `One` Pokud je zjištěna $-$1 eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="3c713-114">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c713-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="3c713-115">Remarks</span></span>

<span data-ttu-id="3c713-116">Pokud jsou pole základu a qubit různými délkami, operace se nezdaří.</span><span class="sxs-lookup"><span data-stu-id="3c713-116">If the basis array and qubit array are different lengths, then the operation will fail.</span></span>