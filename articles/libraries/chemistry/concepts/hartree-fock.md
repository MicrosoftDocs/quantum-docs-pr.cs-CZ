---
title: Hartree – Fock teorie
description: Seznamte se s Hartree – Fock teoreticky, což je jednoduchý způsob, jak vytvořit počáteční stav pro systémy na více systémů.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: 6fa63cbe13fe98565ffb42b56f3ade86720cedb3
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904447"
---
# <a name="hartreefock-theory"></a><span data-ttu-id="d0434-103">Hartree – teorie Fock</span><span class="sxs-lookup"><span data-stu-id="d0434-103">Hartree–Fock Theory</span></span>

<span data-ttu-id="d0434-104">Nejdůležitějším množstvím v simulaci nestavových funkcí je například základní stav, což je minimální energetická eigenvector matice Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="d0434-104">Perhaps the most important quantity in quantum chemistry simulation is the ground state, which is the minimum energy eigenvector of the Hamiltonian matrix.</span></span>
<span data-ttu-id="d0434-105">Důvodem je to, že u většiny molekul v množství pokojové teploty, jako jsou reakční míry, se zachází z bezplatných rozdílů energie mezi stavy, které popisují začátek a konec kroku v reakci na reakci a za pokojovou teplotu, např. mezilehlé. stav jsou obvykle stavy země.</span><span class="sxs-lookup"><span data-stu-id="d0434-105">This is because for most molecules at room temperature quantities such as reaction rates are dominated by free energy differences between quantum states that describe the beginning and end of a step in a reaction pathway and at room temperature such intermediate state are usually ground states.</span></span>
<span data-ttu-id="d0434-106">I když je stav vozovky obvykle moc velký, nemusíte se učit (dokonce i u počítače s velkým množstvím), protože se jedná o distribuci s exponenciálně velkým počtem konfigurací.</span><span class="sxs-lookup"><span data-stu-id="d0434-106">While the ground state is typically too hard to learn (even with a quantum computer) because it is a distribution over an exponentially large number of configurations.</span></span>
<span data-ttu-id="d0434-107">Množství, jako je pozemní energie, se může naučit.</span><span class="sxs-lookup"><span data-stu-id="d0434-107">Quantities such as ground state energy can be learned.</span></span>
<span data-ttu-id="d0434-108">Pokud má například $ \ket{\psi} $ jakýkoliv čistý stav, pak \begin{Equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{Equation} poskytuje střední energii, kterou má systém v tomto stavu.</span><span class="sxs-lookup"><span data-stu-id="d0434-108">For example, if $\ket{\psi}$ is any pure quantum state then \begin{equation} E = \bra{ \psi } \hat{H} \ket{\psi} \end{equation} gives the mean energy that the system has in that state.</span></span>
<span data-ttu-id="d0434-109">Stav země je pak stav, který poskytuje nejmenší takovou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="d0434-109">The ground state then is the state that gives the smallest such value.</span></span> <span data-ttu-id="d0434-110">Výsledkem je, že volba stavu, který je co nejblíže skutečnému stavu, je velmi důležitý pro odhad energie buď přímo (jak se provádí v variaci eigensolvers), nebo prostřednictvím odhadu fáze.</span><span class="sxs-lookup"><span data-stu-id="d0434-110">As a result, choosing a state that is as close as possible to the true ground state is vitally important for estimating the energy either directly (as is done in variational eigensolvers) or through phase estimation.</span></span>

<span data-ttu-id="d0434-111">Hartree – teoretická Fock představuje jednoduchý způsob, jak vytvořit počáteční stav pro systémy s více poli.</span><span class="sxs-lookup"><span data-stu-id="d0434-111">Hartree–Fock theory gives a simple way to construct the initial state for quantum systems.</span></span> <span data-ttu-id="d0434-112">Výsledkem je jedna Slatera determinanta pro základní stav systému.</span><span class="sxs-lookup"><span data-stu-id="d0434-112">It yields a single Slater-determinant approximation to the ground state of a quantum system.</span></span> <span data-ttu-id="d0434-113">Za tímto účelem vyhledá rotaci v rámci Fock místa, které minimalizuje stav energie na zemi.</span><span class="sxs-lookup"><span data-stu-id="d0434-113">To that end, it finds a rotation within Fock-space that minimizes the ground state energy.</span></span> <span data-ttu-id="d0434-114">Konkrétně pro systém $N $ Electrons metoda provádí rotační \begin{Equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket{0} \mapsto \ prod_ {j = 0} ^ {N-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket{0}\defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket{0}, \end{Equation} pomocí anti-Hermitian (tj. $u =-u ^ \dagger $) Matrix $u = \ sum_ {pq} u_ {pq} a ^ \ dagger_p a_q $.</span><span class="sxs-lookup"><span data-stu-id="d0434-114">In particular, for a system of $N$ electrons the method performs the rotation \begin{equation} \prod_{j=0}^{N-1} a^\dagger_j \ket{0} \mapsto \prod_{j=0}^{N-1} e^{u} a^\dagger_j e^{-u} \ket{0}\defeq\prod_{j=0}^{N-1}  \widetilde{a}^\dagger_j  \ket{0}, \end{equation} with an anti-Hermitian (i.e. $u= -u^\dagger$) matrix $u = \sum_{pq} u_{pq} a^\dagger_p a_q$.</span></span> <span data-ttu-id="d0434-115">Je potřeba poznamenat, že matice $u $ představuje rotace Orbital a $ \widetilde{a} ^ \ dagger_j $ a $ \widetilde{a} _j $ představují operátory vytváření a Annihilation pro Electrons, které zaujímají Hartree – Fock molekulární číselník orbitals.</span><span class="sxs-lookup"><span data-stu-id="d0434-115">It should be noted that the matrix $u$ represents the orbital rotations and $\widetilde{a}^\dagger_j$ and $\widetilde{a}_j$ represent creation and annihilation operators for electrons occupying Hartree–Fock molecular spin-orbitals.</span></span>


<span data-ttu-id="d0434-116">Matice $u $ je pak optimalizovaná tak, aby se minimalizovala očekávaná hodnota Energy $ \bra{0} \ prod_ {j = 0} ^ {N-1} \widetilde{a}\_j H \prod\_{k = 0} ^ {N-1} \widetilde{a} ^ \ dagger_k \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="d0434-116">The matrix $u$ is then optimized to minimize the expected energy $\bra{0} \prod_{j=0}^{N-1}  \widetilde{a}\_j  H \prod\_{k=0}^{N-1}  \widetilde{a}^\dagger_k\ket{0}$.</span></span> <span data-ttu-id="d0434-117">I když takové problémy s optimalizací můžou být pevně tvrdé, v praxi se Hartree algoritmus Fock, takže se v praxi rychle konverguje k problému s optimalizací téměř optimálního řešení, zejména pro molekuly v prostředí rovnováhy.</span><span class="sxs-lookup"><span data-stu-id="d0434-117">While such optimization problems may be generically hard, in practice the Hartree–Fock algorithm tends to rapidly converge to a near-optimal solution to the optimization problem, especially for closed-shell molecules in the equilibrium geometries.</span></span> <span data-ttu-id="d0434-118">Tyto stavy můžeme specifikovat jako instanci objektu `FermionWavefunction`.</span><span class="sxs-lookup"><span data-stu-id="d0434-118">We may specify these states as an instance of the `FermionWavefunction` object.</span></span> <span data-ttu-id="d0434-119">Například stav $a ^ \ dagger_{1}^ \ dagger_{2}a ^ \ dagger_{6}\ket{0}$ je vytvořena instance v knihovně chemie následujícím způsobem.</span><span class="sxs-lookup"><span data-stu-id="d0434-119">For instance, the state $a^\dagger_{1}a^\dagger_{2}a^\dagger_{6}\ket{0}$ is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
<span data-ttu-id="d0434-120">Je také možné indexovat funkce vln pomocí `SpinOrbital` indexy a následně tyto indexy převést na celá čísla.</span><span class="sxs-lookup"><span data-stu-id="d0434-120">It is also possible to index wave functions with `SpinOrbital` indices, and then convert these indices to integers as follows.</span></span>
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="d0434-121">Nejefektivnější funkce o Hartree – Fock je to, že poskytuje stav bez stavu, který nemá žádný entanglement mezi Electrons.</span><span class="sxs-lookup"><span data-stu-id="d0434-121">The most striking feature about Hartree–Fock theory is that it yields a quantum state that has no entanglement between the electrons.</span></span>
<span data-ttu-id="d0434-122">To znamená, že často poskytuje vhodný kvalitativní popis vlastností molekulových systémů.</span><span class="sxs-lookup"><span data-stu-id="d0434-122">This means that it often provides a suitable qualitative description of properties of molecular systems.</span></span> 

<span data-ttu-id="d0434-123">Stav Hartree-Fock může být také znovu vytvořen z `FermionHamiltonian` následujícím způsobem.</span><span class="sxs-lookup"><span data-stu-id="d0434-123">The Hartree-Fock state may also be reconstructed from a `FermionHamiltonian`  as follows.</span></span>
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

<span data-ttu-id="d0434-124">Získání přesných výsledků, zejména pro silně korelační systémy, ale vyžaduje stavy, které překračují rámec Hartree – Fock teorie.</span><span class="sxs-lookup"><span data-stu-id="d0434-124">However, obtaining accurate results, especially for strongly correlated systems, necessitate quantum states that go beyond Hartree–Fock theory.</span></span>
