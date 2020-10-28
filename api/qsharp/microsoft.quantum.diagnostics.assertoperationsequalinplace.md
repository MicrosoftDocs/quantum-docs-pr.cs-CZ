---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: Operace AssertOperationsEqualInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 407a139da816281346eb06849f81e91b83202653
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698152"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="b87f9-102">Operace AssertOperationsEqualInPlace</span><span class="sxs-lookup"><span data-stu-id="b87f9-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="b87f9-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b87f9-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b87f9-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b87f9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b87f9-105">Tyto dvě operace vyhodnotí, že jsou identické pro všechny vstupní stavy.</span><span class="sxs-lookup"><span data-stu-id="b87f9-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="b87f9-106">Tento kontrolní výraz je implementován pomocí kontroly akce operací ve všech stavech formuláře $V _0 \otimes... \otimes V_ {n-1} $, kde $V _k $ je jedna ze stavů $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ a $ \ket{i} $ (+ 1 Eigenstate of Pauli Y operator).</span><span class="sxs-lookup"><span data-stu-id="b87f9-106">This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).</span></span>

<span data-ttu-id="b87f9-107">Tento kontrolní výraz používá $n $ qubits a vyžaduje více volání operací, které jsou porovnány.</span><span class="sxs-lookup"><span data-stu-id="b87f9-107">This assertion uses $n$ qubits and requires multiple calls of the operations being compared.</span></span>

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="b87f9-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="b87f9-108">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="b87f9-109">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b87f9-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b87f9-110">Počet qubits $n $, na kterých operace `givenU` fungují a `expectedU` pracují.</span><span class="sxs-lookup"><span data-stu-id="b87f9-110">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="b87f9-111">předané: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b87f9-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b87f9-112">Bude zkontrolována operace na $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="b87f9-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="b87f9-113">očekávalo se: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ.</span><span class="sxs-lookup"><span data-stu-id="b87f9-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="b87f9-114">Operace reference na $n $ qubits, která se má `givenU` Porovnat s.</span><span class="sxs-lookup"><span data-stu-id="b87f9-114">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b87f9-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b87f9-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="b87f9-116">Odkazy</span><span class="sxs-lookup"><span data-stu-id="b87f9-116">References</span></span>

<span data-ttu-id="b87f9-117">Základem stavů $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ a $ \ket{i} $ je Chuang-Nielsen základ, který je popsaný v části [ *i. L. Čuangština, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).</span><span class="sxs-lookup"><span data-stu-id="b87f9-117">The basis of states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ is the Chuang-Nielsen basis, described in [ *I. L. Chuang, M. A. Nielsen* ](https://arxiv.org/abs/quant-ph/9610001).</span></span>

## <a name="see-also"></a><span data-ttu-id="b87f9-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="b87f9-118">See Also</span></span>

- [<span data-ttu-id="b87f9-119">Microsoft. AssertOperationsEqualReferenced. Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="b87f9-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)