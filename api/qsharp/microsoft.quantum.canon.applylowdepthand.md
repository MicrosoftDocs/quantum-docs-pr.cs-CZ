---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: Operace ApplyLowDepthAnd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 7fa9d9bf2f1905bf1b59e783d7bceb8cb2e09fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841709"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="b605b-102">Operace ApplyLowDepthAnd</span><span class="sxs-lookup"><span data-stu-id="b605b-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="b605b-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b605b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b605b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b605b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b605b-105">Invertuje daný cílový qubit, pokud je a pouze v případě, že oba ovládací prvky qubits jsou v 1 stavu s T-hloubkou 1, pomocí měření k provedení sousedící operace.</span><span class="sxs-lookup"><span data-stu-id="b605b-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b605b-106">Popis</span><span class="sxs-lookup"><span data-stu-id="b605b-106">Description</span></span>

<span data-ttu-id="b605b-107">Invertuje `target` pouze v případě, že jsou oba ovládací prvky 1, ale předpokládá, že `target` je ve stavu 0.</span><span class="sxs-lookup"><span data-stu-id="b605b-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="b605b-108">Operace má T-Count 4, T-Depth 1 a vyžaduje jeden pomocný qubit a může proto být vhodnější pro operaci CCNOT, pokud `target` je známo, že má hodnotu 0.</span><span class="sxs-lookup"><span data-stu-id="b605b-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="b605b-109">Sousední funkce této operace měří na základě měření a nevyžaduje žádné brány T a žádné pomocné qubity.</span><span class="sxs-lookup"><span data-stu-id="b605b-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="b605b-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="b605b-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="b605b-111">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b605b-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b605b-112">Qubit prvního ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="b605b-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="b605b-113">Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b605b-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b605b-114">Druhý qubit ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="b605b-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b605b-115">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b605b-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b605b-116">Cílová pomocná qubit; musí být ve stavu 0.</span><span class="sxs-lookup"><span data-stu-id="b605b-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="b605b-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b605b-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="b605b-118">Reference</span><span class="sxs-lookup"><span data-stu-id="b605b-118">References</span></span>

- <span data-ttu-id="b605b-119">Cody Novotný: "nové konstrukce pro bránu Toffoli odolné proti chybám", fyz. rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) doi: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="b605b-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="b605b-120">Petra Selinger: "okruhy T-Depth One", fyz. A 87, 042302, 2013 [arXiv: 1210.0974](https://arxiv.org/abs/1210.0974) doi: 10.1103/PhysRevA. 87.042302</span><span class="sxs-lookup"><span data-stu-id="b605b-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>