---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: Operace RobustPhaseEstimation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 3e6774e2fe348668840cdc08fe3a070ec3d82a6d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216077"
---
# <a name="robustphaseestimation-operation"></a><span data-ttu-id="856ed-102">Operace RobustPhaseEstimation</span><span class="sxs-lookup"><span data-stu-id="856ed-102">RobustPhaseEstimation operation</span></span>

<span data-ttu-id="856ed-103">Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="856ed-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="856ed-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="856ed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="856ed-105">Provádí robustní neiterativní algoritmus odhadu neiteračních procesorů pro dané Oracle `U` a eigenstate a poskytuje jeden odhad ve fázi s proměnlivým škálováním v Heisenberg limitu.</span><span class="sxs-lookup"><span data-stu-id="856ed-105">Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.</span></span>

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="856ed-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="856ed-106">Input</span></span>

### <a name="bitsprecision--int"></a><span data-ttu-id="856ed-107">bitsPrecision: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="856ed-107">bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="856ed-108">To poskytuje odhad $ \phi $ se směrodatnou odchylkou $ \sigma \le 2 \ pi/2 ^ \text{bitsPrecision} $ s použitím řady dotazů, které se mění jako $ \sigma \le 10,7 \pi/\Text{# dotazů} $.</span><span class="sxs-lookup"><span data-stu-id="856ed-108">This provides an estimate of $\phi$ with standard deviation $\sigma \le 2\pi / 2^\text{bitsPrecision}$ using a number of queries scaling like $\sigma \le 10.7 \pi / \text{# of queries}$.</span></span>


### <a name="oracle--discreteoracle"></a><span data-ttu-id="856ed-109">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="856ed-109">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="856ed-110">Operace implementující $U ^ m $ pro celočíselné pravomoci $m $.</span><span class="sxs-lookup"><span data-stu-id="856ed-110">An operation implementing $U^m$ for given integer powers $m$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="856ed-111">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="856ed-111">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="856ed-112">Každé z nich registruje, že $U $ funguje.</span><span class="sxs-lookup"><span data-stu-id="856ed-112">A quantum register that $U$ acts on.</span></span> <span data-ttu-id="856ed-113">Pokud ukládá eigenstate $ \ket{\phi} $ z $U $, pak $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ for $ \phi\in (-\pi, \pi] $ je neznámá fáze.</span><span class="sxs-lookup"><span data-stu-id="856ed-113">If it stores an eigenstate $\ket{\phi}$ of $U$, then $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi\in(-\pi,\pi]$ an unknown phase.</span></span>



## <a name="output--double"></a><span data-ttu-id="856ed-114">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="856ed-114">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="856ed-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="856ed-115">Remarks</span></span>

<span data-ttu-id="856ed-116">V případě velkého počtu dotazů Cramer-Rao dolní meze směrodatné odchylky odhadu hodnot $ \phi $ re\text{$ \sigma \ge 2 \pi/# dotazů.</span><span class="sxs-lookup"><span data-stu-id="856ed-116">In the limit of a large number of queries, Cramer-Rao lower bounds for the standard deviation of the estimate of $\phi$ satisfy $\sigma \ge 2 \pi / \text{# of queries}$.</span></span>

## <a name="references"></a><span data-ttu-id="856ed-117">Reference</span><span class="sxs-lookup"><span data-stu-id="856ed-117">References</span></span>

- <span data-ttu-id="856ed-118">Robustní kalibrace univerzálního Single-Qubit Gate-Set prostřednictvím robustního odhadu fáze Shelby Kimmel, Guang vystoupí hao nízká, Theodora J. Yoder https://arxiv.org/abs/1502.02677</span><span class="sxs-lookup"><span data-stu-id="856ed-118">Robust Calibration of a Universal Single-Qubit Gate-Set via Robust Phase Estimation Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span></span>