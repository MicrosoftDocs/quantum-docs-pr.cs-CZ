---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Operace ApplyFermionicSWAP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 0c470705843a6360df0a72374570d86571397e41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218797"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="83113-102">Operace ApplyFermionicSWAP</span><span class="sxs-lookup"><span data-stu-id="83113-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="83113-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="83113-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="83113-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="83113-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="83113-105">Použije prohození Fermionic.</span><span class="sxs-lookup"><span data-stu-id="83113-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="83113-106">Popis</span><span class="sxs-lookup"><span data-stu-id="83113-106">Description</span></span>

<span data-ttu-id="83113-107">V podstatě dojde k záměně qubits a při použití globální fáze-1, pokud obě qubits mají hodnotu 1.</span><span class="sxs-lookup"><span data-stu-id="83113-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="83113-108">Zachová anti-symmetrization of orbitals.</span><span class="sxs-lookup"><span data-stu-id="83113-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="83113-109">Další informace naleznete v tématu .</span><span class="sxs-lookup"><span data-stu-id="83113-109">See  for more information.</span></span>

<span data-ttu-id="83113-110">Tato operace je reprezentována jednotkovým operátorem \begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="83113-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="83113-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="83113-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="83113-112">Vstup</span><span class="sxs-lookup"><span data-stu-id="83113-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="83113-113">qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="83113-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="83113-114">První qubit, který se má vyměnit</span><span class="sxs-lookup"><span data-stu-id="83113-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="83113-115">qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="83113-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="83113-116">Druhý qubit, který se má prohodit.</span><span class="sxs-lookup"><span data-stu-id="83113-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="83113-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="83113-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="83113-118">Reference</span><span class="sxs-lookup"><span data-stu-id="83113-118">References</span></span>

- [<span data-ttu-id="83113-119">*Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic kanál*, arXiv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="83113-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="83113-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="83113-120">See Also</span></span>

- [<span data-ttu-id="83113-121">Microsoft.. vnitřní. SWAP</span><span class="sxs-lookup"><span data-stu-id="83113-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)