---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: Operace ApplyLowDepthAnd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 4c5e381227bf82415121add38d0c0d2959fb529d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209311"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="0b8a3-102">Operace ApplyLowDepthAnd</span><span class="sxs-lookup"><span data-stu-id="0b8a3-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="0b8a3-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0b8a3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0b8a3-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b8a3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b8a3-105">Invertuje daný cílový qubit, pokud je a pouze v případě, že oba ovládací prvky qubits jsou v 1 stavu s T-hloubkou 1, pomocí měření k provedení sousedící operace.</span><span class="sxs-lookup"><span data-stu-id="0b8a3-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="0b8a3-106">Popis</span><span class="sxs-lookup"><span data-stu-id="0b8a3-106">Description</span></span>

<span data-ttu-id="0b8a3-107">Invertuje `target` pouze v případě, že jsou oba ovládací prvky 1, ale předpokládá, že `target` je ve stavu 0.</span><span class="sxs-lookup"><span data-stu-id="0b8a3-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="0b8a3-108">Operace má T-Count 4, T-Depth 1 a vyžaduje jeden pomocný qubit a může proto být vhodnější pro operaci CCNOT, pokud `target` je známo, že má hodnotu 0.</span><span class="sxs-lookup"><span data-stu-id="0b8a3-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="0b8a3-109">Sousední funkce této operace měří na základě měření a nevyžaduje žádné brány T a žádné pomocné qubity.</span><span class="sxs-lookup"><span data-stu-id="0b8a3-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="0b8a3-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="0b8a3-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="0b8a3-111">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0b8a3-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0b8a3-112">Qubit prvního ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="0b8a3-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="0b8a3-113">Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0b8a3-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0b8a3-114">Druhý qubit ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="0b8a3-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="0b8a3-115">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0b8a3-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0b8a3-116">Cílová pomocná qubit; musí být ve stavu 0.</span><span class="sxs-lookup"><span data-stu-id="0b8a3-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="0b8a3-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0b8a3-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="0b8a3-118">Reference</span><span class="sxs-lookup"><span data-stu-id="0b8a3-118">References</span></span>

- <span data-ttu-id="0b8a3-119">Cody Novotný: "nové konstrukce pro bránu Toffoli odolné proti chybám", fyz. rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) doi: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="0b8a3-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="0b8a3-120">Petra Selinger: "okruhy T-Depth One", fyz. A 87, 042302, 2013 [arXiv: 1210.0974](https://arxiv.org/abs/1210.0974) doi: 10.1103/PhysRevA. 87.042302</span><span class="sxs-lookup"><span data-stu-id="0b8a3-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>