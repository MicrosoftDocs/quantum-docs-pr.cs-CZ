---
title: Korelované vlnové funkce
description: Seznamte se s dynamickými a nedynamickými korelacemi v wavefunctions pomocí knihovny Microsoft pro složení nedodržení.
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.multireference
no-loc:
- Q#
- $$v
ms.openlocfilehash: ab3d90d79c7c14a1ef5b3aa833df49be186f3dd7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856276"
---
# <a name="correlated-wavefunctions"></a><span data-ttu-id="5b6d2-103">Korelované vlnové funkce</span><span class="sxs-lookup"><span data-stu-id="5b6d2-103">Correlated wavefunctions</span></span>

<span data-ttu-id="5b6d2-104">Pro mnoho systémů, zejména v blízkosti geometrie rovnováhy, [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) teoreticky poskytuje kvalitativní popis vlastností molekul prostřednictvím referenčního stavu s jedním determinantem.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-104">For many systems, particularly those near the equilibrium geometry, [Hartree–Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) theory provides a qualitative description of molecular properties through a single-determinant reference state.</span></span> <span data-ttu-id="5b6d2-105">Aby však bylo možné dosáhnout kvantitativní přesnosti, musí být jedna z nich také zvážena z relačních účinků.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-105">However, in order to achieve quantitative accuracy, one must also consider correlation effects.</span></span> 

<span data-ttu-id="5b6d2-106">V tomto kontextu je důležité dinstinguish mezi dynamickými i nedynamickými korelacemi.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-106">In this context, it is important to dinstinguish between dynamic and non-dynamic correlations.</span></span>
<span data-ttu-id="5b6d2-107">Dynamické korelace vznikají od neelectronsch, které by měly zůstat v souvislosti s mezielektronickým přepohonem.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-107">Dynamical correlations arise from the tendency of electrons to stay apart, such as due to interelectronic repulsion.</span></span> <span data-ttu-id="5b6d2-108">Tento efekt můžete modelovat tím, že zvažujete excitations z referenčního stavu Electrons.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-108">This effect can be modelled by considering excitations of electrons out of the reference state.</span></span> <span data-ttu-id="5b6d2-109">Nedynamická korelace nastanou, když je wavefunction na základě dvou nebo více konfigurací v pořadí zeroth, a to i v případě, že dosáhnete pouze kvalitativního popisu systému.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-109">Non-dynamic correlations arise when the wavefunction is dominated by two or more configurations at zeroth order, even to achieve only a qualitative description of the system.</span></span>
<span data-ttu-id="5b6d2-110">To vyžaduje nadpolohu rozhodujících determinantů a je příkladem více wavefunctionch odkazů.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-110">This necessitates a superposition of determinants and is an example of a multireference wavefunction.</span></span>

<span data-ttu-id="5b6d2-111">Knihovna složení poskytuje způsob, jak zadat zeroth objednávky wavefunction pro problém s více odkazy jako nadmnožinu rozhodujících míst.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-111">The chemistry library provides a way to specify a zeroth order wavefunction for the multireference problem as a superposition of determinants.</span></span> <span data-ttu-id="5b6d2-112">Tento přístup, který volá zhuštěné wavefunctionsy, je platný, pokud pouze některé součásti postačují k určení nadpozice.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-112">This approach, which we call sparse multireference wavefunctions, is effective when only a few components suffice to specify the superposition.</span></span> <span data-ttu-id="5b6d2-113">Knihovna také poskytuje metodu pro zahrnutí dynamických korelací na základě jednoho determinantu pomocí generalizované jednotně Ansatz clusteru.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-113">The library also provides a method to include dynamic correlations on top of a single-determinant reference via the generalized unitary coupled-cluster ansatz.</span></span> <span data-ttu-id="5b6d2-114">Kromě toho také sestaví okruhy na základě stavu, které generují tyto stavy na počítači s více stroji.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-114">Furthermore, it also constructs quantum circuits that generate these states on a quantum computer.</span></span> <span data-ttu-id="5b6d2-115">Tyto stavy mohou být zadány ve [schématu Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)a my také poskytujeme funkci pro ruční určení těchto stavů prostřednictvím knihovny složení.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-115">These states may be specified in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), and we also provide the functionality to manually specify these states through the chemistry library.</span></span>

## <a name="sparse-multi-reference-wavefunction"></a><span data-ttu-id="5b6d2-116">Wavefunction zhuštěných více odkazů</span><span class="sxs-lookup"><span data-stu-id="5b6d2-116">Sparse multi-reference wavefunction</span></span>
<span data-ttu-id="5b6d2-117">Stav vícenásobných odkazů $ \ket{\ psi_ {\rm {MCSCF}}} $ se dá explicitně zadat jako lineární kombinace $N $-elektron Slater determininants.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-117">A multi-reference state $\ket{\psi_{\rm {MCSCF}}}$ may be specified explicitly as a linear combination of $N$-electron Slater determininants.</span></span>
<span data-ttu-id="5b6d2-118">\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1, i_2, \cdots, i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots a ^ \ dagger_ {i_N} \ket {0} .</span><span class="sxs-lookup"><span data-stu-id="5b6d2-118">\begin{align} \ket{\psi_{\rm {MCSCF}}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1,i_2,\cdots,i_N} a^\dagger_{i_1}a^\dagger_{i_2}\cdots a^\dagger_{i_N}\ket{0}.</span></span>
<span data-ttu-id="5b6d2-119">\end{align} například stav $ \propto (0,1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0,2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) \ket {0} $ může být uveden v knihovně chemie následujícím způsobem.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-119">\end{align} For example, the state $\propto(0.1 a^\dagger_1a^\dagger_2a^\dagger_6 - 0.2 a^\dagger_2a^\dagger_1a^\dagger_5)\ket{0}$ may be specified in the chemistry library as follows.</span></span>
```csharp
// Create a list of tuples where the first item of each 
// tuple are indices to the creation operators acting on the
// vacuum state, and the second item is the coefficient
// of that basis state.
var superposition = new[] {
    (new[] {1, 2, 6}, 0.1),
    (new[] {2, 1, 5}, -0.2) };

// Create a fermion wavefunction object that represents the superposition.
var wavefunction = new FermionWavefunction<int>(superposition);
```
<span data-ttu-id="5b6d2-120">Tato explicitní reprezentace komponent nadpozice je platná, pokud je třeba zadat pouze některé součásti.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-120">This explicit representation of the superposition components is effective when only a few components need to be specified.</span></span> <span data-ttu-id="5b6d2-121">Při použití této reprezentace by se neměla používat tato reprezentace, pokud je potřeba k přesnému zachycení požadovaného stavu použít spoustu součástí.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-121">One should avoid using this representation when many components are required to accurately capture the desired state.</span></span> <span data-ttu-id="5b6d2-122">Důvodem je, že se jedná o cenu za využití okruhu, která tento stav připraví na počítač s více procesory, který se škáluje alespoň lineárně s počtem komponent na více pozicích a s největší kvadratickou s jednou normou amplitudy pozice.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-122">The reason for this is the gate cost of quantum circuit that prepares this state on a quantum computer, which scales at least linearly with the number of superposition components, and at most quadratically with the one-norm of the superposition amplitudes.</span></span>

## <a name="unitary-coupled-cluster-wavefunction"></a><span data-ttu-id="5b6d2-123">Jednotně kombinovaná wavefunction clusteru</span><span class="sxs-lookup"><span data-stu-id="5b6d2-123">Unitary coupled-cluster wavefunction</span></span>
<span data-ttu-id="5b6d2-124">Pomocí knihovny chemistery je taky možné zadat jednotnou kombinaci wavefunction $ \ket{\ psi_ {\rm {UCC}}} $.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-124">It is also possible to specify a unitary coupled-cluster wavefunction $\ket{\psi_{\rm {UCC}}}$ using the chemistery library.</span></span> <span data-ttu-id="5b6d2-125">V této situaci máme jediný determinant referenčního stavu, například $ \ket{\ psi_ {\rm{SCF}}} $.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-125">In this situation, we have a single-determinant reference state, say, $\ket{\psi_{\rm{SCF}}}$.</span></span> <span data-ttu-id="5b6d2-126">Komponenty pro jednotně wavefunction clustery se pak implicitně určí prostřednictvím jednotkového operátoru, který funguje v referenčním stavu.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-126">The components of the unitary coupled-cluster wavefunction are then specified implicity through a unitary operator acting on a reference state.</span></span>
<span data-ttu-id="5b6d2-127">Tento operátor s jednou jednotkou se běžně zapisuje jako $e ^ {T-T ^ \dagger} $, kde $T-T ^ \dagger $ je operátor Hermitianho clusteru.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-127">This unitary operator is commonly written as $e^{T-T^\dagger}$, where $T-T^\dagger$ is the anti-Hermitian cluster operator.</span></span> <span data-ttu-id="5b6d2-128">Proto \begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-128">Thus \begin{align} \ket{\psi_{\rm {UCC}}} = e^{T-T^\dagger}\ket{\psi_{\rm{SCF}}}.</span></span>
<span data-ttu-id="5b6d2-129">\end{align}</span><span class="sxs-lookup"><span data-stu-id="5b6d2-129">\end{align}</span></span>

<span data-ttu-id="5b6d2-130">Také je běžné rozdělit operátor clusteru $T = T_1 + T_2 + \cdots $ do částí, kde každá část $T _j $ obsahuje označení $j $-tělo.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-130">It is also common to split the cluster operator $T = T_1 + T_2 + \cdots$ into parts, where each part $T_j$ contains $j$-body terms.</span></span> <span data-ttu-id="5b6d2-131">V generalizované kombinaci mezi clustery (jednoduchou) má operátor clusteru s jedním tělem () ve formě \begin{align} T_1 = \ sum_ {pq} T ^ {p} _ {q} a ^ \ dagger_p a_q, \end{align}</span><span class="sxs-lookup"><span data-stu-id="5b6d2-131">In generalized coupled-cluster theory, the one-body cluster operator (singles) is of the form \begin{align} T_1 = \sum_{pq}t^{p}_{q} a^\dagger_p a_q, \end{align}</span></span>

<span data-ttu-id="5b6d2-132">a \begin{align} operátor clusteru (Double) má tvar T_2 = \ sum_ {pqrs} T ^ {pq} _ {RS} a ^ \ dagger_p ^ \ dagger_q a_r a_s.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-132">and two-body cluster operator (doubles) is of the form \begin{align} T_2 = \sum_{pqrs}t^{pq}_{rs} a^\dagger_p a^\dagger_q a_r a_s.</span></span>
<span data-ttu-id="5b6d2-133">\end{align}</span><span class="sxs-lookup"><span data-stu-id="5b6d2-133">\end{align}</span></span>

<span data-ttu-id="5b6d2-134">Je možné, že se jedná o výrazy s vyšším pořadím (Trojnásobky, čtyřikrát atd.), ale ne aktuálně podporované knihovnou chemie.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-134">Higher-order terms (triples, quadruples, etc.) are possible, but not currently supported by the chemistry library.</span></span>

<span data-ttu-id="5b6d2-135">Například nechejte $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} $ a nechte $T = 0,123 a ^ \ dagger_0 A_1 + 0,456 a ^ \ dagger_0a ^ \ dagger_3 a_1 A_2-0,789 a ^ \ dagger_3a ^ \ dagger_2 A_1 A_0 $.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-135">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_1 a^\dagger_2\ket{0}$, and let $T= 0.123 a^\dagger_0 a_1 + 0.456 a^\dagger_0a^\dagger_3 a_1 a_2 - 0.789 a^\dagger_3a^\dagger_2 a_1 a_0$.</span></span> <span data-ttu-id="5b6d2-136">Pak je tento stav vytvořen v knihovně chemie následujícím způsobem.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-136">Then this state is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { 1, 2 };

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {0, 1}, 0.123),
    (new [] {0, 3, 1, 2}, 0.456),
    (new [] {3, 2, 1, 0}, 0.789)
};

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunction = new FermionWavefunction<int>(reference, clusterOperator);
```

<span data-ttu-id="5b6d2-137">Je možné provést explicitní convervation místo toho, aby namísto `SpinOrbital` celočíselných indexů určila indexy.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-137">Spin convervation may be made explicit by instead specifying `SpinOrbital` indices instead of integer indices.</span></span> <span data-ttu-id="5b6d2-138">Můžete například let $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1, \uparrow} a ^ \ dagger_ {2, \downarrow}\ket {0} $ a let $T = 0,123 a ^ \ dagger_ {0, \uparrow} a_ {1, \uparrow} + 0,456 a ^ \ dagger_ {0, \uparrow} a ^ \ dagger_ {3, \downarrow} a_ {1, \uparrow} a_ {2, \downarrow}-0,789 a ^ \ dagger_ {3, \uparrow} a ^ \ dagger_ {2, \uparrow} a_ {1, \uparrow} a_ {0, \uparrow} $ by měl být číselník convserving.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-138">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_{1,\uparrow} a^\dagger_{2, \downarrow}\ket{0}$, and let $T= 0.123 a^\dagger_{0, \uparrow} a_{1, \uparrow} + 0.456 a^\dagger_{0, \uparrow} a^\dagger_{3, \downarrow} a_{1, \uparrow} a_{2, \downarrow} - 0.789 a^\dagger_{3,\uparrow} a^\dagger_{2,\uparrow} a_{1,\uparrow} a_{0, \uparrow}$ be spin convserving.</span></span> <span data-ttu-id="5b6d2-139">Pak je tento stav vytvořen v knihovně chemie následujícím způsobem.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-139">Then this state is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {(0, Spin.u), (1, Spin.u)}, 0.123),
    (new [] {(0, Spin.u), (3, Spin.d), (1, Spin.u), (2, Spin.d)}, 0.456),
    (new [] {(3, Spin.u), (2, Spin.u), (1, Spin.u), (0, Spin.u)}, 0.789)
}.Select(o => (o.Item1.ToSpinOrbitals(), o.Item2);

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(reference, clusterOperator);

// Convert the wavefunction indexed by spin-orbitals to one indexed
// by integers
var wavefunctionInteger = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="5b6d2-140">Nabízíme také pohodlí, která vytvoří výčet pro všechny operátory clusterů konverzující, které annihilate jenom, orbitals a nadchnou jenom na neobsazený číselník.</span><span class="sxs-lookup"><span data-stu-id="5b6d2-140">We also provide a convenience function that enumerates over all spin-conversing cluster operators that annihilate only occupied spin-orbitals and excite to only unoccupied spin-orbitals.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Generate all spin-conversing excitations from spin-orbitals 
// occupied by the reference state to virtual orbitals.
var generatedExcitations = reference.CreateAllUCCSDSingletExcitations(nOrbitals: 3).Excitations;

// This is the list of expected spin-consvering excitations
var expectedExcitations = new[]
{
    new []{ (0, Spin.u), (1,Spin.u)},
    new []{ (2, Spin.u), (1,Spin.u)},
    new []{ (0, Spin.d), (2,Spin.d)},
    new []{ (1, Spin.d), (2,Spin.d)},
    new []{ (0, Spin.u), (0, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.u), (1, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)},
    new []{ (1, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)}
}.Select(o => new IndexOrderedSequence<SpinOrbital>(o.ToLadderSequence()));

// The following two assertions are true, and verify that the generated 
// excitations exactly match the expected excitations.
var bool0 = generatedExcitations.Keys.All(expectedExcitations.Contains);
var bool1 = generatedExcitations.Count() == expectedExcitations.Count();
```
