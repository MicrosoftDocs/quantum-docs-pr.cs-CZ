---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: Operace ApplyAnd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 39ffb9c598b6345c0d63c0c0d9705d84e101cc47
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845191"
---
# <a name="applyand-operation"></a><span data-ttu-id="d85a0-102">Operace ApplyAnd</span><span class="sxs-lookup"><span data-stu-id="d85a0-102">ApplyAnd operation</span></span>

<span data-ttu-id="d85a0-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d85a0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d85a0-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d85a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d85a0-105">Invertuje zadaný cílový qubit, pokud jsou oba ovládací prvky qubits ve 1 stavu, přičemž pomocí měření provede operaci sousedících operací.</span><span class="sxs-lookup"><span data-stu-id="d85a0-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d85a0-106">Popis</span><span class="sxs-lookup"><span data-stu-id="d85a0-106">Description</span></span>

<span data-ttu-id="d85a0-107">Invertuje `target` pouze v případě, že jsou oba ovládací prvky 1, ale předpokládá, že `target` je ve stavu 0.</span><span class="sxs-lookup"><span data-stu-id="d85a0-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="d85a0-108">Operace má T-Count 4, T-Depth 2 a nevyžaduje žádné pomocné qubit a může proto být vhodnější pro operaci CCNOT, pokud `target` je známo, že má hodnotu 0.</span><span class="sxs-lookup"><span data-stu-id="d85a0-108">The operation has T-count 4, T-depth 2 and requires no helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="d85a0-109">Sousední operace této operace měří na základě měření a nevyžaduje žádné brány T.</span><span class="sxs-lookup"><span data-stu-id="d85a0-109">The adjoint of this operation is measurement based and requires no T gates.</span></span>

<span data-ttu-id="d85a0-110">Kontrolované použití této operace nevyžaduje žádné pomocné qubit, `2^c` `Rz` brány a není optimalizované pro hloubku, kde `c` je počet celkových ovládacích prvků qubits, včetně dvou ovládacích prvků z `ApplyAnd` operace.</span><span class="sxs-lookup"><span data-stu-id="d85a0-110">The controlled application of this operation requires no helper qubit, `2^c` `Rz` gates and is not optimized for depth, where `c` is the number of overall control qubits including the two controls from the `ApplyAnd` operation.</span></span>  <span data-ttu-id="d85a0-111">Aplikace řízená pomocí souseda vyžaduje, aby byly `2^c - 1` `Rz` brány (s úhlem dvojnásobku velikosti nesousedících operací), žádné pomocné qubit a není optimalizované pro hloubku.</span><span class="sxs-lookup"><span data-stu-id="d85a0-111">The adjoint controlled application requires `2^c - 1` `Rz` gates (with an angle twice the size of the non-adjoint operation), no helper qubit and is not optimized for depth.</span></span>

## <a name="input"></a><span data-ttu-id="d85a0-112">Vstup</span><span class="sxs-lookup"><span data-stu-id="d85a0-112">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="d85a0-113">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d85a0-113">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d85a0-114">Qubit prvního ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="d85a0-114">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="d85a0-115">Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d85a0-115">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d85a0-116">Druhý qubit ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="d85a0-116">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d85a0-117">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d85a0-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d85a0-118">Cílová pomocná qubit; musí být ve stavu 0.</span><span class="sxs-lookup"><span data-stu-id="d85a0-118">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="d85a0-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d85a0-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="d85a0-120">Reference</span><span class="sxs-lookup"><span data-stu-id="d85a0-120">References</span></span>

- <span data-ttu-id="d85a0-121">Cody Novotný: "nové konstrukce pro bránu Toffoli odolné proti chybám", fyz. rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) doi: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="d85a0-121">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="d85a0-122">Craig Gidney: "snížení nákladů na sčítání, 2. stranu, strana 74, 2018 [arXiv: 1709.06648](https://arxiv.org/abs/1709.06648) doi: 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="d85a0-122">Craig Gidney: "Halving the cost of quantum addition", Quantum 2, page 74, 2018 [arXiv:1709.06648](https://arxiv.org/abs/1709.06648) doi:10.1103/PhysRevA.85.044302</span></span>
- <span data-ttu-id="d85a0-123">Mathias Soeken: "okruhy Oracle a vzor vánoční stromové struktury", [článek na blogu od 19. prosince 2019](https://msoeken.github.io/blog_qac.html) (Poznámka: vysvětlení více řízených konstrukcí)</span><span class="sxs-lookup"><span data-stu-id="d85a0-123">Mathias Soeken: "Quantum Oracle Circuits and the Christmas Tree Pattern", [Blog article from December 19, 2019](https://msoeken.github.io/blog_qac.html) (note: explains the multiple controlled construction)</span></span>