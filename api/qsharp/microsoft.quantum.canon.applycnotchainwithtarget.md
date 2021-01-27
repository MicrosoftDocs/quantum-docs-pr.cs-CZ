---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: Operace ApplyCNOTChainWithTarget
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: ba1a4e99c411a4718b5a09fdcd57a7239eb4dbd6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845116"
---
# <a name="applycnotchainwithtarget-operation"></a><span data-ttu-id="d24db-102">Operace ApplyCNOTChainWithTarget</span><span class="sxs-lookup"><span data-stu-id="d24db-102">ApplyCNOTChainWithTarget operation</span></span>

<span data-ttu-id="d24db-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d24db-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d24db-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d24db-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d24db-105">Vypočítá paritu pole qubits do cílového qubit.</span><span class="sxs-lookup"><span data-stu-id="d24db-105">Computes the parity of an array of qubits into a target qubit.</span></span>

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d24db-106">Popis</span><span class="sxs-lookup"><span data-stu-id="d24db-106">Description</span></span>

<span data-ttu-id="d24db-107">Pokud je pole zpočátku ve stavu $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\Text{Target}}} $, konečný stav je dán v $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\Text{Target}}} $.</span><span class="sxs-lookup"><span data-stu-id="d24db-107">If the array is initially in the state $\ket{q_0} \ket{q_1} \cdots \ket{q_{\text{target}}}$, the final state is given by $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{\text{target}}}$.</span></span>

## <a name="input"></a><span data-ttu-id="d24db-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="d24db-108">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="d24db-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d24db-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d24db-110">Pole qubits, na kterém je vypočítána parita.</span><span class="sxs-lookup"><span data-stu-id="d24db-110">Array of qubits on which the parity is computed.</span></span>


### <a name="targetqubit--qubit"></a><span data-ttu-id="d24db-111">targetQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d24db-111">targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d24db-112">Konečný qubit, do kterého je parita ' qubits ' XORed.</span><span class="sxs-lookup"><span data-stu-id="d24db-112">Final qubit into which the parity of 'qubits' is XORed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d24db-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d24db-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d24db-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d24db-114">Remarks</span></span>

<span data-ttu-id="d24db-115">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="d24db-115">The following are equivalent:</span></span>

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

<span data-ttu-id="d24db-116">a</span><span class="sxs-lookup"><span data-stu-id="d24db-116">and</span></span>

```qsharp
ApplyCNOTChain(qs);
```