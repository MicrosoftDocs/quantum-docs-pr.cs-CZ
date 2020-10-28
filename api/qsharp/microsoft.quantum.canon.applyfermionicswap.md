---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Operace ApplyFermionicSWAP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 25dd91b200700d1474cf27bf1d0fa71d57f2e09b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705377"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="b20ef-102">Operace ApplyFermionicSWAP</span><span class="sxs-lookup"><span data-stu-id="b20ef-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="b20ef-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b20ef-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b20ef-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b20ef-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b20ef-105">Použije prohození Fermionic.</span><span class="sxs-lookup"><span data-stu-id="b20ef-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="b20ef-106">Popis</span><span class="sxs-lookup"><span data-stu-id="b20ef-106">Description</span></span>

<span data-ttu-id="b20ef-107">V podstatě dojde k záměně qubits a při použití globální fáze-1, pokud obě qubits mají hodnotu 1.</span><span class="sxs-lookup"><span data-stu-id="b20ef-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="b20ef-108">Zachová anti-symmetrization of orbitals.</span><span class="sxs-lookup"><span data-stu-id="b20ef-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="b20ef-109">Další informace naleznete v tématu .</span><span class="sxs-lookup"><span data-stu-id="b20ef-109">See  for more information.</span></span>

<span data-ttu-id="b20ef-110">Tato operace je reprezentována jednotkovým operátorem \begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="b20ef-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="b20ef-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="b20ef-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="b20ef-112">Vstup</span><span class="sxs-lookup"><span data-stu-id="b20ef-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="b20ef-113">qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b20ef-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b20ef-114">První qubit, který se má vyměnit</span><span class="sxs-lookup"><span data-stu-id="b20ef-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="b20ef-115">qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b20ef-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b20ef-116">Druhý qubit, který se má prohodit.</span><span class="sxs-lookup"><span data-stu-id="b20ef-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b20ef-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b20ef-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="b20ef-118">Odkazy</span><span class="sxs-lookup"><span data-stu-id="b20ef-118">References</span></span>

- [<span data-ttu-id="b20ef-119">*Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic kanál* , arXiv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="b20ef-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan* , arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="b20ef-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="b20ef-120">See Also</span></span>

- [<span data-ttu-id="b20ef-121">Microsoft.. vnitřní. SWAP</span><span class="sxs-lookup"><span data-stu-id="b20ef-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)