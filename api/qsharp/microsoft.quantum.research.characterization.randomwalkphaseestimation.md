---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: Operace RandomWalkPhaseEstimation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: 5e0c0871b916ff51b85dec8703111788b5204bc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697553"
---
# <a name="randomwalkphaseestimation-operation"></a><span data-ttu-id="fcc5a-102">Operace RandomWalkPhaseEstimation</span><span class="sxs-lookup"><span data-stu-id="fcc5a-102">RandomWalkPhaseEstimation operation</span></span>

<span data-ttu-id="fcc5a-103">Obor názvů: [Microsoft.. Research. charakterizace](xref:Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="fcc5a-103">Namespace: [Microsoft.Quantum.Research.Characterization](xref:Microsoft.Quantum.Research.Characterization)</span></span>

<span data-ttu-id="fcc5a-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fcc5a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fcc5a-105">Provádí odhad iterativní fáze pomocí náhodného prohledání přibližné bayesovského rozhodování odvození na výsledky klasických měření z daných Oracle a eigenstate.</span><span class="sxs-lookup"><span data-stu-id="fcc5a-105">Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.</span></span>

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="fcc5a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="fcc5a-106">Input</span></span>

### <a name="initialmean--double"></a><span data-ttu-id="fcc5a-107">initialMean: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fcc5a-107">initialMean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fcc5a-108">Střední hodnota počátečního normálního povýšení při předchozí distribuci přes $ \phi $</span><span class="sxs-lookup"><span data-stu-id="fcc5a-108">Mean of the initial normal prior distribution over $\phi$.</span></span>


### <a name="initialstddev--double"></a><span data-ttu-id="fcc5a-109">initialStdDev: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fcc5a-109">initialStdDev : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fcc5a-110">Směrodatná odchylka počátečního normálního rozdělení při předchozí distribuci na $ \phi $</span><span class="sxs-lookup"><span data-stu-id="fcc5a-110">Standard deviation of the initial normal prior distribution over $\phi$.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="fcc5a-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fcc5a-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fcc5a-112">Počet měření, která se mají přijmout do konečného dodatečného odhadu.</span><span class="sxs-lookup"><span data-stu-id="fcc5a-112">Number of measurements to be accepted into the final posterior estimate.</span></span>


### <a name="maxmeasurements--int"></a><span data-ttu-id="fcc5a-113">maxMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fcc5a-113">maxMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fcc5a-114">Celkový počet měření, než může být proveden před tím, než je operace považována za neúspěšnou.</span><span class="sxs-lookup"><span data-stu-id="fcc5a-114">Total number of measurements than can be taken before the operation is considered to have failed.</span></span>


### <a name="unwind--int"></a><span data-ttu-id="fcc5a-115">unwind: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fcc5a-115">unwind : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fcc5a-116">Počet výsledků, které mají být zapomenout při selhání kontroly konzistence.</span><span class="sxs-lookup"><span data-stu-id="fcc5a-116">Number of results to forget when consistency checks fail.</span></span>


### <a name="oracle--continuousoracle"></a><span data-ttu-id="fcc5a-117">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="fcc5a-117">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="fcc5a-118">Operace představující jednotnou $U $, kterou $U (t) \ket{\phi} = e ^ {i t \phi}\ket{\phi} $ for eigenstates $ \ket{\phi} $ s neznámou fází $ \phi \in \mathbb{R} ^ + $.</span><span class="sxs-lookup"><span data-stu-id="fcc5a-118">An operation representing a unitary $U$ such that $U(t)\ket{\phi} = e^{i t \phi}\ket{\phi}$ for eigenstates $\ket{\phi}$ with unknown phase $\phi \in \mathbb{R}^+$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="fcc5a-119">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fcc5a-119">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fcc5a-120">Registr, na kterém $U $ pracuje.</span><span class="sxs-lookup"><span data-stu-id="fcc5a-120">A register that $U$ acts on.</span></span>



## <a name="output--double"></a><span data-ttu-id="fcc5a-121">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fcc5a-121">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fcc5a-122">Konečný odhad $ \hat{\phi} \mathrel{: =} \expect [\phi] $, kde se očekává, že je na začátku všechna přijatá data.</span><span class="sxs-lookup"><span data-stu-id="fcc5a-122">The final estimate $\hat{\phi} \mathrel{:=} \expect[\phi]$ , where the expectation is over the posterior given all accepted data.</span></span>

## <a name="remarks"></a><span data-ttu-id="fcc5a-123">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fcc5a-123">Remarks</span></span>

### <a name="iterative-phase-estimation-and-eigenstates"></a><span data-ttu-id="fcc5a-124">Odhad iterační fáze a Eigenstates</span><span class="sxs-lookup"><span data-stu-id="fcc5a-124">Iterative Phase Estimation and Eigenstates</span></span>

<span data-ttu-id="fcc5a-125">Obecně platí, že vstupní registr `eigenstate` nemusí být eigenstate $ \ket{\phi} $ of $U $, ale může být na pozici nad eigenstates.</span><span class="sxs-lookup"><span data-stu-id="fcc5a-125">In general, the input register `eigenstate` need not be an eigenstate $\ket{\phi}$ of $U$, but can be a superposition over eigenstates.</span></span> <span data-ttu-id="fcc5a-126">Předpokládejme, že vstupní stav je dán \begin{align} \ket{\psi} & = \sum \_ {j} \Alpha \_ j \ket{\phi \_ j}, \end{align}, kde $ \{ \Alpha \_ j \} $ jsou složité, například $ \sum \_ j | \Alpha \_ j | ^ 2 = $1 a kde $U \ket{\phi \_ j} = \phi \_ j\ket {\ fí \_ j} $.</span><span class="sxs-lookup"><span data-stu-id="fcc5a-126">Suppose that the input state is given by \begin{align} \ket{\psi} & = \sum\_{j} \alpha\_j \ket{\phi\_j}, \end{align} where $\{\alpha\_j\}$ are complex coefficients such that $\sum\_j |\alpha\_j|^2 = 1$ and where $U\ket{\phi\_j} = \phi\_j\ket{\phi\_j}$.</span></span>

<span data-ttu-id="fcc5a-127">Následný odhad iterační fáze se nakonec konverguje na jeden eigenstate, jak je popsáno v příručce pro [vývoj](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span><span class="sxs-lookup"><span data-stu-id="fcc5a-127">Then, performing iterative phase estimation will eventually converge to a single eigenstate, as described in the [development guide](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span></span>

### <a name="experiment-design"></a><span data-ttu-id="fcc5a-128">Experimentovat návrh</span><span class="sxs-lookup"><span data-stu-id="fcc5a-128">Experiment Design</span></span>

<span data-ttu-id="fcc5a-129">Doba měření $t $ a inverze úhlů $ \theta $ předaná do `oracle` jsou zvolena v souladu s *heuristikou pro odhad částic* , \Begin{align} \theta \sim \Pr (\phi), \quad t \approx \frac {1} {\variance{\phi}}.</span><span class="sxs-lookup"><span data-stu-id="fcc5a-129">The measurement times $t$ and inversion angles $\theta$ passed to `oracle` are chosen according to the *particle guess heuristic* , \begin{align} \theta \sim \Pr(\phi),\quad t \approx \frac{1}{\variance{\phi}}.</span></span>
<span data-ttu-id="fcc5a-130">\end{align} tato heuristická metoda je ideální pro snížení očekávané další odchylky v iterativní fázi odhadu v rámci předběžného normálního předběžného.</span><span class="sxs-lookup"><span data-stu-id="fcc5a-130">\end{align} This heuristic is optimal for reducing the expected posterior variance in iterative phase estimation under the assumption of a normal prior.</span></span>

### <a name="optimality"></a><span data-ttu-id="fcc5a-131">Optimální výkon</span><span class="sxs-lookup"><span data-stu-id="fcc5a-131">Optimality</span></span>

<span data-ttu-id="fcc5a-132">Tato operace se blíží optimálnímu Estimator pro fázi $ \phi $, jak je vyhodnocená pomocí $L kvadratické ztráty (\phi, \hat{\phi}) \mathrel{: =} (\phi-\hat{\phi}) ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="fcc5a-132">This operation approximates the optimal estimator for the phase $\phi$, as evaluated using the quadratic loss $L(\phi, \hat{\phi}) \mathrel{:=} (\phi - \hat{\phi})^2$.</span></span>

<span data-ttu-id="fcc5a-133">Další informace o statistice iterativní fáze odhadu najdete v tématu [odhad fáze bayesovského rozhodování](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="fcc5a-133">See [Bayesian Phase Estimation](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) for more details on the statistics of iterative phase estimation.</span></span>

## <a name="references"></a><span data-ttu-id="fcc5a-134">Odkazy</span><span class="sxs-lookup"><span data-stu-id="fcc5a-134">References</span></span>

- <span data-ttu-id="fcc5a-135">Pro trajekty *et al.* 2011 [doi: 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [arXiv: 1110.3067](https://arxiv.org/abs/1110.3067).</span><span class="sxs-lookup"><span data-stu-id="fcc5a-135">Ferrie *et al.* 2011 [doi:10/tfx](https://doi.org/10.1007/s11128-012-0407-6), [arXiv:1110.3067](https://arxiv.org/abs/1110.3067).</span></span>
- <span data-ttu-id="fcc5a-136">Wiebe *et al.* 2013 [doi: 10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv: 1309.0876](https://arxiv.org/abs/1309.0876)</span><span class="sxs-lookup"><span data-stu-id="fcc5a-136">Wiebe *et al.* 2013 [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv:1309.0876](https://arxiv.org/abs/1309.0876)</span></span>
- <span data-ttu-id="fcc5a-137">Wiebe a granade 2018 *(v přípravě)* .</span><span class="sxs-lookup"><span data-stu-id="fcc5a-137">Wiebe and Granade 2018 *(in preparation)* .</span></span>