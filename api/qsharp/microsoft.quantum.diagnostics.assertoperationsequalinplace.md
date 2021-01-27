---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: Operace AssertOperationsEqualInPlace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 7c330ebdc156e60713a734d39a3600ee1326563c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853487"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="74147-102">Operace AssertOperationsEqualInPlace</span><span class="sxs-lookup"><span data-stu-id="74147-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="74147-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="74147-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="74147-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="74147-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="74147-105">Tyto dvě operace vyhodnotí, že jsou identické pro všechny vstupní stavy.</span><span class="sxs-lookup"><span data-stu-id="74147-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="74147-106">Tento kontrolní výraz je implementován pomocí kontroly akce operací ve všech stavech formuláře $V _0 \otimes... \otimes V_ {n-1} $, kde $V _k $ je jedna ze stavů $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ a $ \ket{i} $ (+ 1 Eigenstate of Pauli Y operator).</span><span class="sxs-lookup"><span data-stu-id="74147-106">This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).</span></span>

<span data-ttu-id="74147-107">Tento kontrolní výraz používá $n $ qubits a vyžaduje více volání operací, které jsou porovnány.</span><span class="sxs-lookup"><span data-stu-id="74147-107">This assertion uses $n$ qubits and requires multiple calls of the operations being compared.</span></span>

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="74147-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="74147-108">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="74147-109">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="74147-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="74147-110">Počet qubits $n $, na kterých operace `givenU` fungují a `expectedU` pracují.</span><span class="sxs-lookup"><span data-stu-id="74147-110">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="74147-111">předané: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="74147-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="74147-112">Bude zkontrolována operace na $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="74147-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="74147-113">očekává se: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="74147-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="74147-114">Operace reference na $n $ qubits, která se má `givenU` Porovnat s.</span><span class="sxs-lookup"><span data-stu-id="74147-114">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="74147-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="74147-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="74147-116">Reference</span><span class="sxs-lookup"><span data-stu-id="74147-116">References</span></span>

<span data-ttu-id="74147-117">Základem stavů $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ a $ \ket{i} $ je Chuang-Nielsen základ, který je popsaný v části [ *i. L. Čuangština, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).</span><span class="sxs-lookup"><span data-stu-id="74147-117">The basis of states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ is the Chuang-Nielsen basis, described in [ *I. L. Chuang, M. A. Nielsen* ](https://arxiv.org/abs/quant-ph/9610001).</span></span>

## <a name="see-also"></a><span data-ttu-id="74147-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="74147-118">See Also</span></span>

- [<span data-ttu-id="74147-119">Microsoft. AssertOperationsEqualReferenced. Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="74147-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)