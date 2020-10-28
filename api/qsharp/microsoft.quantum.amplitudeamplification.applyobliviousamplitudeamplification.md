---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: Operace ApplyObliviousAmplitudeAmplification
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: a1bda344b1097c7ab3240bc6d9cd0d8df80b9662
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707743"
---
# <a name="applyobliviousamplitudeamplification-operation"></a><span data-ttu-id="2fc56-102">Operace ApplyObliviousAmplitudeAmplification</span><span class="sxs-lookup"><span data-stu-id="2fc56-102">ApplyObliviousAmplitudeAmplification operation</span></span>

<span data-ttu-id="2fc56-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="2fc56-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="2fc56-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2fc56-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2fc56-105">Oblivious amplitudy tím, že se určí částečné odrazy.</span><span class="sxs-lookup"><span data-stu-id="2fc56-105">Oblivious amplitude amplification by specifying partial reflections.</span></span>

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2fc56-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2fc56-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="2fc56-107">fáze: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="2fc56-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="2fc56-108">Fáze částečných odrazů</span><span class="sxs-lookup"><span data-stu-id="2fc56-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="2fc56-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="2fc56-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="2fc56-110">Operátor reflexe o počátečním stavu pomocného zápisu</span><span class="sxs-lookup"><span data-stu-id="2fc56-110">Reflection operator about start state of auxiliary register</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="2fc56-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="2fc56-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="2fc56-112">Operátor reflexe pro cílový stav pomocného zápisu</span><span class="sxs-lookup"><span data-stu-id="2fc56-112">Reflection operator about target state of auxiliary register</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="2fc56-113">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="2fc56-113">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="2fc56-114">Jednotkový typ Oracle $O $ `ObliviousOracle` , který pracuje společně na pomocných a systémových registrech.</span><span class="sxs-lookup"><span data-stu-id="2fc56-114">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system registers.</span></span>


### <a name="auxiliaryregister--qubit"></a><span data-ttu-id="2fc56-115">auxiliaryRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2fc56-115">auxiliaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2fc56-116">Pomocný registr</span><span class="sxs-lookup"><span data-stu-id="2fc56-116">Auxiliary register</span></span>


### <a name="systemregister--qubit"></a><span data-ttu-id="2fc56-117">systemRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2fc56-117">systemRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2fc56-118">Systémový registr</span><span class="sxs-lookup"><span data-stu-id="2fc56-118">System register</span></span>



## <a name="output--unit"></a><span data-ttu-id="2fc56-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2fc56-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2fc56-120">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2fc56-120">Remarks</span></span>

<span data-ttu-id="2fc56-121">S ohledem na určitý pomocný stav spuštění $ \ket{\Text{Start}} \_ a $, konkrétní pomocný cílový stav $ \ket{\Text{Target}} a \_ $ a jakýkoli stav systému $ \ket{\psi} \_ s $, Předpokládejme, že \begin{align} O\ket {\ text {Start}} \_ a\ket {\ psí} \_ s = \lambda\ket{\Text{Target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\Text{Target} ^ \perp} \_ a\cdots \end{align} pro některé jednotkové $U $.</span><span class="sxs-lookup"><span data-stu-id="2fc56-121">Given a particular auxiliary start state $\ket{\text{start}}\_a$, a particular auxiliary target state $\ket{\text{target}}\_a$, and any system state $\ket{\psi}\_s$, suppose that \begin{align} O\ket{\text{start}}\_a\ket{\psi}\_s= \lambda\ket{\text{target}}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{\text{target}^\perp}\_a\cdots \end{align} for some unitary $U$.</span></span>
<span data-ttu-id="2fc56-122">V rámci posloupnosti odrazů týkajících se stavů Start a target u pomocného registru, který prochází aplikace `signalOracle` a její sousedníci, pravděpodobnost úspěchu při použití U může být změněna.</span><span class="sxs-lookup"><span data-stu-id="2fc56-122">By a sequence of reflections about the start and target states on the auxiliary register interleaved by applications of `signalOracle` and its adjoint, the success probability of applying U may be altered.</span></span>

<span data-ttu-id="2fc56-123">Ve většině případů `auxiliaryRegister` je inicializován ve stavu $ \ket{\Text{Start}} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="2fc56-123">In most cases, `auxiliaryRegister` is initialized in the state $\ket{\text{start}}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="2fc56-124">Odkazy</span><span class="sxs-lookup"><span data-stu-id="2fc56-124">References</span></span>

<span data-ttu-id="2fc56-125">Seznamte se s </span><span class="sxs-lookup"><span data-stu-id="2fc56-125">See</span></span>

- <span data-ttu-id="2fc56-126">[ *D.W. bobuloviny, ráno dceřiné, r. Cleve, r. Kothari, R.D. Somma*](https://arxiv.org/abs/1312.1414) pro standardní verzi.</span><span class="sxs-lookup"><span data-stu-id="2fc56-126">[ *D.W. Berry, A.M. Childs, R. Cleve, R. Kothari, R.D. Somma* ](https://arxiv.org/abs/1312.1414) for the standard version.</span></span>
  <span data-ttu-id="2fc56-127">Seznamte se s </span><span class="sxs-lookup"><span data-stu-id="2fc56-127">See</span></span>
- <span data-ttu-id="2fc56-128">[ *G.H. nízká, I.L. Čuangština*](https://arxiv.org/abs/1610.06546) pro generalizaci na částečná odrazy.</span><span class="sxs-lookup"><span data-stu-id="2fc56-128">[ *G.H. Low, I.L. Chuang* ](https://arxiv.org/abs/1610.06546) for a generalization to partial reflections.</span></span>