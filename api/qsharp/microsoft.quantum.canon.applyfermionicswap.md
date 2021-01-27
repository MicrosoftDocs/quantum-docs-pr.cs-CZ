---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Operace ApplyFermionicSWAP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 334f407a32dabc8f4e0a1a29c8f06a1b9f40dc59
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845049"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="e0a23-102">Operace ApplyFermionicSWAP</span><span class="sxs-lookup"><span data-stu-id="e0a23-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="e0a23-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e0a23-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e0a23-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e0a23-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e0a23-105">Použije prohození Fermionic.</span><span class="sxs-lookup"><span data-stu-id="e0a23-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e0a23-106">Popis</span><span class="sxs-lookup"><span data-stu-id="e0a23-106">Description</span></span>

<span data-ttu-id="e0a23-107">V podstatě dojde k záměně qubits a při použití globální fáze-1, pokud obě qubits mají hodnotu 1.</span><span class="sxs-lookup"><span data-stu-id="e0a23-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="e0a23-108">Zachová anti-symmetrization of orbitals.</span><span class="sxs-lookup"><span data-stu-id="e0a23-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="e0a23-109">Další informace naleznete v tématu .</span><span class="sxs-lookup"><span data-stu-id="e0a23-109">See  for more information.</span></span>

<span data-ttu-id="e0a23-110">Tato operace je reprezentována jednotkovým operátorem \begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="e0a23-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="e0a23-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e0a23-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="e0a23-112">Vstup</span><span class="sxs-lookup"><span data-stu-id="e0a23-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="e0a23-113">qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e0a23-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e0a23-114">První qubit, který se má vyměnit</span><span class="sxs-lookup"><span data-stu-id="e0a23-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="e0a23-115">qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e0a23-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e0a23-116">Druhý qubit, který se má prohodit.</span><span class="sxs-lookup"><span data-stu-id="e0a23-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e0a23-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e0a23-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="e0a23-118">Reference</span><span class="sxs-lookup"><span data-stu-id="e0a23-118">References</span></span>

- [<span data-ttu-id="e0a23-119">*Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic kanál*, arXiv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="e0a23-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="e0a23-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="e0a23-120">See Also</span></span>

- [<span data-ttu-id="e0a23-121">Microsoft.. vnitřní. SWAP</span><span class="sxs-lookup"><span data-stu-id="e0a23-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)