---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: Operace ApplyCNOTChainWithTarget
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705440"
---
# <a name="applycnotchainwithtarget-operation"></a><span data-ttu-id="ef787-102">Operace ApplyCNOTChainWithTarget</span><span class="sxs-lookup"><span data-stu-id="ef787-102">ApplyCNOTChainWithTarget operation</span></span>

<span data-ttu-id="ef787-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ef787-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ef787-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ef787-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ef787-105">Vypočítá paritu pole qubits do cílového qubit.</span><span class="sxs-lookup"><span data-stu-id="ef787-105">Computes the parity of an array of qubits into a target qubit.</span></span>

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="ef787-106">Popis</span><span class="sxs-lookup"><span data-stu-id="ef787-106">Description</span></span>

<span data-ttu-id="ef787-107">Pokud je pole zpočátku ve stavu $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\Text{Target}}} $, konečný stav je dán v $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\Text{Target}}} $.</span><span class="sxs-lookup"><span data-stu-id="ef787-107">If the array is initially in the state $\ket{q_0} \ket{q_1} \cdots \ket{q_{\text{target}}}$, the final state is given by $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{\text{target}}}$.</span></span>

## <a name="input"></a><span data-ttu-id="ef787-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="ef787-108">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="ef787-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ef787-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ef787-110">Pole qubits, na kterém je vypočítána parita.</span><span class="sxs-lookup"><span data-stu-id="ef787-110">Array of qubits on which the parity is computed.</span></span>


### <a name="targetqubit--qubit"></a><span data-ttu-id="ef787-111">targetQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ef787-111">targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ef787-112">Konečný qubit, do kterého je parita ' qubits ' XORed.</span><span class="sxs-lookup"><span data-stu-id="ef787-112">Final qubit into which the parity of 'qubits' is XORed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ef787-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ef787-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ef787-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ef787-114">Remarks</span></span>

<span data-ttu-id="ef787-115">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="ef787-115">The following are equivalent:</span></span>

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

<span data-ttu-id="ef787-116">a</span><span class="sxs-lookup"><span data-stu-id="ef787-116">and</span></span>

```qsharp
ApplyCNOTChain(qs);
```