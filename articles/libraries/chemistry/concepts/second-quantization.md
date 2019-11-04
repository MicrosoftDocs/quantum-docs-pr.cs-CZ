---
title: Druhý kvantizační | Microsoft Docs
description: Druhý kvantizační koncepční dokumentace
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
ms.openlocfilehash: b3cc7eb8139d2df6e02de371ccf7a423e58ea76d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2019
ms.locfileid: "73210408"
---
# <a name="second-quantization"></a><span data-ttu-id="38da6-103">Druhý kvantizační</span><span class="sxs-lookup"><span data-stu-id="38da6-103">Second Quantization</span></span>

<span data-ttu-id="38da6-104">Druhý kvantizační podívá na problém elektronické struktury v jiném objektivu.</span><span class="sxs-lookup"><span data-stu-id="38da6-104">Second quantization looks at the problem of electronic structure through a different lens.</span></span>
<span data-ttu-id="38da6-105">Místo přiřazování každé z $N _e $ Electrons ke konkrétnímu stavu (nebo Orbital) Druhá kvantizační každou Orbital sleduje a ukládá, zda je v každé z nich přítomna elektronická část a ve stejnou dobu automaticky zajišťuje vlastnosti symetrie odpovídající funkce Wave.</span><span class="sxs-lookup"><span data-stu-id="38da6-105">Rather than assigning each of the $N_e$ electrons to a specific state (or orbital), second quantization tracks each orbital and stores whether there is an electron present in each of them and at the same time automatically ensures symmetry properties of the corresponding wave function.</span></span>
<span data-ttu-id="38da6-106">To je důležité, protože umožňuje určit modely chemickéch procesorů, aniž byste se museli starat o symmetrizing stav vstupu (jak je vyžadováno pro fermions), a také proto, že druhý kvantizační umožňuje simulaci takových modelů pomocí malých stavů. pocítac.</span><span class="sxs-lookup"><span data-stu-id="38da6-106">This is important because it allows quantum chemistry models to be specified without having to worry about anti-symmetrizing the input state (as is required for fermions) and also because second quantization allows such models to be simulated using small quantum computers.</span></span>

<span data-ttu-id="38da6-107">Jako příklad druhé kvantizační v akci se předpokládá, že $ \psi_0\cdots \psi_{N-1} $ je orthonormal sada prostorových orbitals.</span><span class="sxs-lookup"><span data-stu-id="38da6-107">As an example of second quantization in action, let's assume that $\psi_0\cdots \psi_{N-1}$ are an orthonormal set of spatial orbitals.</span></span>
<span data-ttu-id="38da6-108">Tyto orbitals se volí tak, aby reprezentovaly systém co nejpřesněji v uvažovaném rámci omezeného základního nastavení.</span><span class="sxs-lookup"><span data-stu-id="38da6-108">These orbitals are chosen to represent the system as accurately as possible within the finite basis set considered.</span></span>
<span data-ttu-id="38da6-109">Běžným příkladem takových orbitals jsou atomické orbitalsy, které tvoří eigenbasis pro Atom vodík.</span><span class="sxs-lookup"><span data-stu-id="38da6-109">A common example of such orbitals are atomic orbitals which form an eigenbasis for the hydrogen atom.</span></span>
<span data-ttu-id="38da6-110">Vzhledem k tomu, že Electrons mají dva stavy otočení, dvě Electrons mohou být crammed do každého takového prostorového Orbital.</span><span class="sxs-lookup"><span data-stu-id="38da6-110">Because electrons have two spin states, two electrons can be crammed into each such spatial orbital.</span></span>
<span data-ttu-id="38da6-111">To znamená, že platnými základními stavy jsou formuláře $ \psi_{0, \uparrow}, \ldots, \psi_{N-1, \uparrow}, \psi_{0, \downarrow}, \ldots, \psi_{N-1, \downarrow} $ WHERE $ \uparrow $ a $ \downarrow $ jsou popisky, které určují dva eigenstatesy stupně otáčení Svoboda.</span><span class="sxs-lookup"><span data-stu-id="38da6-111">That is to say, the valid basis states are of the form $\psi_{0,\uparrow},\ldots,\psi_{N-1,\uparrow}, \psi_{0,\downarrow},\ldots,\psi_{N-1,\downarrow}$ where $\uparrow$ and $\downarrow$ are labels that specify the two eigenstates of the spin degree of freedom.</span></span>
<span data-ttu-id="38da6-112">Tento kombinovaný index pro $ (j, \sigma) $ pro $ \sigma \in \{\uparrow, \downarrow\}$ se nazývá míchy, protože ukládá jak prostor, tak i stupeň volnosti.</span><span class="sxs-lookup"><span data-stu-id="38da6-112">This combined index of $(j,\sigma)$ for $\sigma \in \{\uparrow,\downarrow\}$ is called a spin-orbital because it stores both the spatial as well as the spin degree of freedom.</span></span>
<span data-ttu-id="38da6-113">V knihovně chemie jsou orbitalsy uloženy ve struktuře dat `SpinOrbital` a jsou vytvořeny následujícím způsobem.</span><span class="sxs-lookup"><span data-stu-id="38da6-113">In the chemistry library, spin-orbitals are stored in a `SpinOrbital` data structure, and are created as follows.</span></span>

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

<span data-ttu-id="38da6-114">To znamená, že můžeme považovat základ pro otočení i prostorové části funkce Wave jako $ \psi_{0} \cdots \psi_{2N-1} $, kde každá z indexů teď představuje výčet $ (j, \sigma) $.</span><span class="sxs-lookup"><span data-stu-id="38da6-114">This means that we can formally think of the basis for both the spin and spatial part of the wave function as $\psi_{0} \cdots \psi_{2N-1}$ where each of the indices now is an enumeration of a $(j,\sigma)$.</span></span>
<span data-ttu-id="38da6-115">Jeden možný výčet je $g (j, \sigma) = j + N\sigma $.</span><span class="sxs-lookup"><span data-stu-id="38da6-115">One possible enumeration is $g(j,\sigma) = j+N\sigma'$.</span></span>
<span data-ttu-id="38da6-116">Další možný výčet je $h (j, \sigma) = 2 \* j + \sigma $.</span><span class="sxs-lookup"><span data-stu-id="38da6-116">Another possible enumeration is $h(j,\sigma) = 2\*j + \sigma$.</span></span>
<span data-ttu-id="38da6-117">Knihovna složení doby provozu může tyto konvence použít a na orbitals v takovém kódování lze vytvořit instanci následujícím způsobem.</span><span class="sxs-lookup"><span data-stu-id="38da6-117">The quantum chemistry library can use these conventions, and the spin-orbitals in such an encoding can be instantiated as follows.</span></span>

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

<span data-ttu-id="38da6-118">V případě systémů fermionic se Pauli princip vyloučení zabrání tomu, aby se v jakémkoli Orbital ve stejnou dobu zobrazoval více než jeden elektron.</span><span class="sxs-lookup"><span data-stu-id="38da6-118">For fermionic systems, the Pauli exclusion principle prevents more than one electron from being present in any spin-orbital at the same time.</span></span>
<span data-ttu-id="38da6-119">To znamená, že můžeme zapsat dva právní stavy pro $ \psi_1 $ as \begin{Equation} \psi_1 \rightarrow \begin{Cases} \ket{0}_1 & \Text{if $ \psi_1 $ není obsazené </span><span class="sxs-lookup"><span data-stu-id="38da6-119">This means that we can write the two legal states for $\psi_1$ as \begin{equation} \psi_1 \rightarrow \begin{cases} \ket{0}_1 & \text{if $\psi_1$ is not occupied,} </span></span>\\\
<span data-ttu-id="38da6-120">\ket{1}_1 & \Text{if $ \psi_1 $ je obsazené.}</span><span class="sxs-lookup"><span data-stu-id="38da6-120">\ket{1}_1 & \text{if $\psi_1$ is occupied.}</span></span> <span data-ttu-id="38da6-121">\end{Cases} \end{Equation} toto kódování je skvělé pro počítače, protože to znamená, že je možné uložit elektronické povolání jako jeden bit.</span><span class="sxs-lookup"><span data-stu-id="38da6-121">\end{cases} \end{equation} This encoding is great for quantum computers because it means that we can store the electronic occupation as a single quantum bit.</span></span>

<span data-ttu-id="38da6-122">Stavy povolání pro orbitals $2N $ se můžou podobně ukládat v $2N $ qubits.</span><span class="sxs-lookup"><span data-stu-id="38da6-122">The occupation states for the $2N$ spin orbitals can similarly be stored in $2N$ qubits.</span></span>
<span data-ttu-id="38da6-123">Pokud například $N = $2, pak stav $ $ \ket{0} \ket{1} \ket{1} \ket{0}, $ $</span><span class="sxs-lookup"><span data-stu-id="38da6-123">As an example, if $N=2$ then the state $$ \ket{0} \ket{1} \ket{1} \ket{0}, $$</span></span>

<span data-ttu-id="38da6-124">by odpovídaly číselníku orbitals $1 $ a $2 $, který je obsazený zbývajícím prázdným.</span><span class="sxs-lookup"><span data-stu-id="38da6-124">would correspond to spin orbitals $1$ and $2$ being occupied with the remainder empty.</span></span>
<span data-ttu-id="38da6-125">Podobně platí, že stav $ $ \ket{0} \equiv \ket{0} _{0} \cdots \ket{0}_ {N-1}, $ $</span><span class="sxs-lookup"><span data-stu-id="38da6-125">Similarly, the state $$ \ket{0} \equiv \ket{0}_{0} \cdots \ket{0}_{N-1}, $$</span></span>

<span data-ttu-id="38da6-126">nemá žádný Electrons a je známý jako "podtlak State".</span><span class="sxs-lookup"><span data-stu-id="38da6-126">has no electrons and is known as the 'vacuum state'.</span></span>

<span data-ttu-id="38da6-127">Krásné vedlejší účinky druhé kvantizační je, že už nemusíme explicitně sledovat anti-symetrii stavu nedodržení.</span><span class="sxs-lookup"><span data-stu-id="38da6-127">A beautiful side-effect of second quantization is that we no longer have to explicitly keep track of the anti-symmetry of the quantum state.</span></span>
<span data-ttu-id="38da6-128">To proto, že jak uvidíme, anti-symetrie státu se místo toho reprezentuje prostřednictvím pravidel ochrany před přístavování operátorů, kteří vytvářejí a zničí elektronické povolání míchy Orbital.</span><span class="sxs-lookup"><span data-stu-id="38da6-128">This is because, as we will see, the anti-symmetry of the state represents itself instead through the anti-commutation rules of the operators that create and destroy electronic occupations of a spin orbital.</span></span>

## <a name="fermionic-operators"></a><span data-ttu-id="38da6-129">Fermionic operátory</span><span class="sxs-lookup"><span data-stu-id="38da6-129">Fermionic operators</span></span>

<span data-ttu-id="38da6-130">Dva základní operátory, které fungují na quantized základních vektorů, se nazývají vytváření a Annihilation operátory.</span><span class="sxs-lookup"><span data-stu-id="38da6-130">The two fundamental operators that act on the second-quantized basis vectors are known as creation and annihilation operators.</span></span>
<span data-ttu-id="38da6-131">Tyto operátory vkládají nebo zničí Electrons v konkrétním umístění.</span><span class="sxs-lookup"><span data-stu-id="38da6-131">These operators insert or destroy electrons at a particular location.</span></span>
<span data-ttu-id="38da6-132">Jsou označené $a ^ \dagger_j $ a $a _J $.</span><span class="sxs-lookup"><span data-stu-id="38da6-132">These are denoted $a^\dagger_j$ and $a_j$ respectively.</span></span>

<span data-ttu-id="38da6-133">Například \begin{Align} a ^ \dagger_1 \ket{0}_1 = \ket{1}_1, \quad a ^ \dagger_1 \ket{1}_1 = 0, \quad A_1 \ket{0}_1 = 0, \quad A_1 \ket{1}_1 = \ket{0}_1.</span><span class="sxs-lookup"><span data-stu-id="38da6-133">For example, \begin{align} a^\dagger_1 \ket{0}_1 = \ket{1}_1,\quad a^\dagger_1 \ket{1}_1 = 0,\quad a_1 \ket{0}_1 = 0,\quad a_1 \ket{1}_1 = \ket{0}_1.</span></span>
<span data-ttu-id="38da6-134">\end{align} Všimněte si, že tady $a ^ \dagger_1 \ket{1}_1 = 0 $ a $a _1 \ket{0}_1 $ Dej nulové vektor not $ \ket{0}_1 $.</span><span class="sxs-lookup"><span data-stu-id="38da6-134">\end{align} Note that here $a^\dagger_1 \ket{1}_1=0$ and $a_1 \ket{0}_1$ yield the zero-vector not $\ket{0}_1$.</span></span>
<span data-ttu-id="38da6-135">Takové operátory proto nejsou ani Hermitian ani nejednotná.</span><span class="sxs-lookup"><span data-stu-id="38da6-135">Such operators are therefore neither Hermitian nor unitary.</span></span>
<span data-ttu-id="38da6-136">Annihilation operátory pro obecné vytváření a používání se zastupují pomocí typu <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1>.</span><span class="sxs-lookup"><span data-stu-id="38da6-136">We represent general creation and annihilation operators using the <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> type.</span></span>
<span data-ttu-id="38da6-137">Například jeden operátor vytvoření je reprezentován následujícím způsobem.</span><span class="sxs-lookup"><span data-stu-id="38da6-137">For instance, a single creation operator is represented as follow.</span></span>

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

<span data-ttu-id="38da6-138">Tyto operátory můžeme také vyjádřit Express $ $ \ket{0} \ket{1} \ket{1} \ket{0} = a ^ \dagger_1 a ^ \dagger_2 \ket{0}^ {\otimes 4}.</span><span class="sxs-lookup"><span data-stu-id="38da6-138">Also using such operators we can express $$ \ket{0} \ket{1} \ket{1} \ket{0} = a^\dagger_1 a^\dagger_2 \ket{0}^{\otimes 4}.</span></span>
<span data-ttu-id="38da6-139">$ $ Tato sekvence operátorů by se vytvořila v rámci knihovny simulace Hamiltonian C# pomocí kódu, který je podobný případu s jedním otočením Orbital, který se považuje za výše:</span><span class="sxs-lookup"><span data-stu-id="38da6-139">$$ This sequence of operators would be constructed within the Hamiltonian simulation library using C# code that is similar to the single-spin orbital case considered above above:</span></span>
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

<span data-ttu-id="38da6-140">V případě systému $k $ Fermions ve druhém kvantizační akce operátoru vytvoření $a ^ \dagger_i $ je poskytnuta $ $ a ^ \dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \ldots, 1_i , \ldots, n_k}, $ $ a $ $ a ^ \dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k} = 0, kde $S _i = \sum_{j < i} a ^ \dagger_j a_j $ měří celkový počet Fermions, které jsou ve stavu jedné částice a které mají index $j < i $.</span><span class="sxs-lookup"><span data-stu-id="38da6-140">For a system of $k$ Fermions, in second quantization the action of the creation operator $a^\dagger_i$ is given by $$ a^\dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k } = (-1)^{S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $$ and $$ a^\dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k } = 0, $$ where $S_i = \sum_{j<i} a^\dagger_j a_j$ measures the total number of Fermions that are in the state of a single particle and that have an index $j < i$.</span></span>

<span data-ttu-id="38da6-141">Třetí operátor se také často používá ve druhém quantized reprezentace.</span><span class="sxs-lookup"><span data-stu-id="38da6-141">A third operator is also often used in second quantized representations.</span></span>
<span data-ttu-id="38da6-142">Tento operátor je označován jako operátor Number a je definován pomocí \begin{Equation} n_i = a ^ \dagger_i a_i.</span><span class="sxs-lookup"><span data-stu-id="38da6-142">This operator is known as the number operator and is defined by \begin{equation} n_i = a^\dagger_i a_i.</span></span>
<span data-ttu-id="38da6-143">\end{Equation} Tento operátor počítá povolání daného číselníku Orbital, což znamená \begin{align} n_i \ket{0}_i & = 0 \ č.</span><span class="sxs-lookup"><span data-stu-id="38da6-143">\end{equation} This operator counts the occupation of a given spin orbital, which is to say \begin{align} n_i \ket{0}_i &= 0\nonumber</span></span>\\\
<span data-ttu-id="38da6-144">n_i \ket{1}_i & = \ket{1}_i.</span><span class="sxs-lookup"><span data-stu-id="38da6-144">n_i \ket{1}_i &= \ket{1}_i.</span></span>
<span data-ttu-id="38da6-145">\end{align} podobná výše uvedeným příkladům `FermionTerm` tento číselný operátor je konstruován takto.</span><span class="sxs-lookup"><span data-stu-id="38da6-145">\end{align} Similar to the above `FermionTerm` examples, this number operator is constructed as follows.</span></span>
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have ommitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

<span data-ttu-id="38da6-146">Subtlety se při použití operátorů vytváření nebo Annihilation v systémech fermionic objeví.</span><span class="sxs-lookup"><span data-stu-id="38da6-146">A subtlety emerges though when using creation or annihilation operators in fermionic systems.</span></span>
<span data-ttu-id="38da6-147">Vyžadujeme, aby jakýkoliv platný stav v nenáročném stavu byl v rámci výměny popisků příliš symetrický.</span><span class="sxs-lookup"><span data-stu-id="38da6-147">We require that any valid quantum state is anti-symmetric under exchange of labels.</span></span>
<span data-ttu-id="38da6-148">To znamená, že $ $ a ^ \dagger_2 a ^ \dagger_1 \ket{0} =-a ^ \dagger_1 a ^ \dagger_2 \ket{0}.</span><span class="sxs-lookup"><span data-stu-id="38da6-148">This means that $$ a^\dagger_2 a^\dagger_1 \ket{0} = -a^\dagger_1 a^\dagger_2 \ket{0}.</span></span>
<span data-ttu-id="38da6-149">$ $ Tyto operátory jsou označovány jako "" anti-dojíždění "a obecně pro všechny $i, j $ máme \begin{Align} a ^ \dagger_i a ^ \dagger_j =-(1-\delta_{i, j}) ^ \dagger_j a ^ \dagger_i, \quad a ^ \dagger_i a_j = \delta_{i, j}-a_j a ^ \dagger_i.</span><span class="sxs-lookup"><span data-stu-id="38da6-149">$$ Such operators are said to 'anti-commute' and in general for any $i, j$ we have that \begin{align} a^\dagger_i a^\dagger_j  = -(1-\delta_{i,j})a^\dagger_j a^\dagger_i,\quad a^\dagger_i a_j =\delta_{i,j} - a_j a^\dagger_i.</span></span>
<span data-ttu-id="38da6-150">\end{align} takže následující dvě instance <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> jsou považovány za neekvivalentní</span><span class="sxs-lookup"><span data-stu-id="38da6-150">\end{align} Thus the following two <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instances are considered inequivalent</span></span>
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

<span data-ttu-id="38da6-151">Požadavek na to, aby každá z operátorů vytváření byla dojíždění, znamená, že použití druhé reprezentace quantized předkládá výzvy, na které čelí anti-symetrie Fermions.</span><span class="sxs-lookup"><span data-stu-id="38da6-151">The requirement that each of the creation operators anti-commute means that using a second quantized representation does obviate the challenges faced by the anti-symmetry of Fermions.</span></span>
<span data-ttu-id="38da6-152">Místo toho se výzva v naší definici operátorů vytváření objeví znovu.</span><span class="sxs-lookup"><span data-stu-id="38da6-152">Instead the challenge re-emerges in our definition of the creation operators.</span></span> 

<span data-ttu-id="38da6-153">Pomocí pravidel pro účely ochrany proti dojíždění některé instance `LadderSequence` ve skutečnosti odpovídají stejné sekvenci fermionicch operátorů, někdy až po znaménku mínus.</span><span class="sxs-lookup"><span data-stu-id="38da6-153">Using the anti-commutation rules, some `LadderSequence` instances actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="38da6-154">Zvažte například Hamiltonian $a _0 ^ \dagger A_1 ^ \dagger A_1 A_0 =-A_1 ^ \dagger A_0 ^ \dagger A_1 A_0 $.</span><span class="sxs-lookup"><span data-stu-id="38da6-154">For instance, consider the Hamiltonian $a_0^\dagger a_1^\dagger a_1 a_0 = - a_1^\dagger a_0^\dagger a_1 a_0$.</span></span>
<span data-ttu-id="38da6-155">To vám umožní definovat kanonické řazení pro každé `FermionTerm`.</span><span class="sxs-lookup"><span data-stu-id="38da6-155">This motivates us to define a canonical ordering for every `FermionTerm`.</span></span>
<span data-ttu-id="38da6-156">Jakékoli `FermionTerm` jsou automaticky vloženy do kanonického pořadí následujícím způsobem.</span><span class="sxs-lookup"><span data-stu-id="38da6-156">Any `FermionTerm` is automatically put into canonical order as follows.</span></span>
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a><span data-ttu-id="38da6-157">Druhý – quantized Fermionic Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="38da6-157">Second-Quantized Fermionic Hamiltonian</span></span>

<span data-ttu-id="38da6-158">Je možné, že Hamiltonian v modelech neunsurprisingch hodnot [pro elektronické systémy](xref:microsoft.quantum.chemistry.concepts.quantummodels) se dají zapisovat z podmínek vytváření a annihilationch operátorů.</span><span class="sxs-lookup"><span data-stu-id="38da6-158">It is perhaps unsurprising that the Hamiltonian in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) can be written in terms of creation and annihilation operators.</span></span>
<span data-ttu-id="38da6-159">Konkrétně Pokud $ \psi\_j $ jsou orbitals, které tvoří základ, potom</span><span class="sxs-lookup"><span data-stu-id="38da6-159">In particular, if $\psi\_j$ are the spin orbitals that form the basis then</span></span>

<span data-ttu-id="38da6-160">\begin{Equation} \hat{H} = \sum\_{pq} H\_{pq} a ^ \dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} H\_{pqrs} a ^ \dagger\_p a ^ \dagger\_q a\_RA\_s + h\_{\textrm NUC}, \label{EQ: totalHam} \end{Equation} kde $h\_{\textrm NUC} $ je jaderná energie (což je konstanta pod odhadem Oppenheimer) a</span><span class="sxs-lookup"><span data-stu-id="38da6-160">\begin{equation} \hat{H} = \sum\_{pq} h\_{pq}a^\dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} h\_{pqrs}a^\dagger\_p a^\dagger\_q a\_ra\_s +h\_{\textrm nuc},\label{eq:totalHam} \end{equation} where $h\_{\textrm nuc}$ is the nuclear energy (which is a constant under the Born-Oppenheimer approximation) and</span></span>

<span data-ttu-id="38da6-161">\begin{align} h\_{pq} & = \int\_{-\infty} ^ \infty \psi \left\*\_p (x\_1) \frac{\nabla (-\right ^ 2}{2} + V (x\_1) \psi) \mathrm{d}\_q (x\_1) 3x ^ @no__ t_9_ 1, \end{align}</span><span class="sxs-lookup"><span data-stu-id="38da6-161">\begin{align} h\_{pq} &= \int\_{-\infty}^\infty \psi^\*\_p(x\_1) \left(-\frac{\nabla^2}{2} +V(x\_1)\right)  \psi\_q(x\_1)\mathrm{d}^3x\_1, \end{align}</span></span>

<span data-ttu-id="38da6-162">kde $V (x) $ je potenciál v poli střední hodnoty a</span><span class="sxs-lookup"><span data-stu-id="38da6-162">where $V(x)$ is the mean-field potential, and</span></span>

<span data-ttu-id="38da6-163">\begin{align} h\_{pqrs} & = \int\_{-\infty} ^ \infty \int\_{-\infty} ^ \infty\psi\_p ^\*(x\_1) \psi\_q ^\*(x\_2) \left (\frac{1}{| x_1-x_2 |} \ Right) \psi\_r (x\_2) \psi\_s (x\_1) \mathrm{d} ^ 3x\_1 \ mathrm {d} ^ 3x\_2. \ Label {EQ: integrs} \end{align}</span><span class="sxs-lookup"><span data-stu-id="38da6-163">\begin{align} h\_{pqrs} &= \int\_{-\infty}^\infty \int\_{-\infty}^\infty\psi\_p^\*(x\_1)\psi\_q^\*(x\_2) \left(\frac{1}{|x_1-x_2|} \right)\psi\_r(x\_2)\psi\_s(x\_1)\mathrm{d}^3x\_1\mathrm{d}^3x\_2.\label{eq:integrals} \end{align}</span></span>

<span data-ttu-id="38da6-164">Výrazy $h\_{pq} $ jsou odkazovány jako integrály, protože všechny takové výrazy zahrnují pouze jeden Electrons a podobně $h\_{pqrs} $ jsou dva elektronické integrály.</span><span class="sxs-lookup"><span data-stu-id="38da6-164">The terms $h\_{pq}$ are refered to as one-electron integrals because all such terms only involve single electrons and likewise $h\_{pqrs}$ are the two-electron integrals.</span></span>
<span data-ttu-id="38da6-165">Jsou označovány jako integrály, protože výpočet hodnot těchto koeficientů vyžaduje integrál.</span><span class="sxs-lookup"><span data-stu-id="38da6-165">They are called integrals because computing the values of these coefficients requires an integral.</span></span>
<span data-ttu-id="38da6-166">Jedna elektronická podmínka popisuje kinetiku vlastní energie jednotlivých Electrons a jejich interakce s elektrickými poli Nuclei.</span><span class="sxs-lookup"><span data-stu-id="38da6-166">The one electron terms describe the kinetic energy of the individual electrons and their interactions with the electric fields of the nuclei.</span></span>
<span data-ttu-id="38da6-167">Dva elektronické integrály na druhé straně popisují interakce mezi Electrons.</span><span class="sxs-lookup"><span data-stu-id="38da6-167">The two-electron integrals on the other hand describe the interactions between the electrons.</span></span>

<span data-ttu-id="38da6-168">Intuition, co znamenají tyto výrazy, se dají mohli z operátorů vytváření a Annihilation, které tvoří každou z nich.</span><span class="sxs-lookup"><span data-stu-id="38da6-168">An intuition for what these terms mean can be gleaned from the creation and annihilation operators that comprise each of them.</span></span>
<span data-ttu-id="38da6-169">Například $h _ {pq} a ^ \dagger_p a_q $ popisuje Orbital skákající od míchy Orbital $q $ k otočení $p $.</span><span class="sxs-lookup"><span data-stu-id="38da6-169">For example, $h_{pq}a^\dagger_p a_q$ describes the electron hopping from spin orbital $q$ to spin orbital $p$.</span></span>
<span data-ttu-id="38da6-170">Podobně pojem $h _ {pqrs} a ^ \dagger_p a ^ \dagger_q a_r a_s $ (pro odlišná $p, q, r, s $) popisuje dva Electrons ve míchách orbitals $r $ a $s $ a končí v orbitals $p $ a $q $.</span><span class="sxs-lookup"><span data-stu-id="38da6-170">Similarly, the term $h_{pqrs} a^\dagger_p a^\dagger_q a_r a_s$ (for distinct $p,q,r,s$) describes two electrons in spin orbitals $r$ and $s$ scattering off of each other and ending up in spin orbitals $p$ and $q$.</span></span>
<span data-ttu-id="38da6-171">Pokud $r = q $ a $p = s $, pak $h _ {prrp} a ^ \dagger_p a ^ \dagger_r a_r a_p = H_ {prrp} n_p n_r $ poskytuje snížení energie spojené s těmito dvěma electronsy blízko sebe, ale nepopisuje dynamický proces.</span><span class="sxs-lookup"><span data-stu-id="38da6-171">If $r=q$ and $p=s$ then $h_{prrp} a^\dagger_p a^\dagger_r a_r a_p = h_{prrp} n_p n_r$ gives the energy penalty associated with the two electrons being near each other, but does not describe a dynamical process.</span></span>

<span data-ttu-id="38da6-172">Takový Hamiltonians můžeme zastupovat pomocí třídy `FermionHamiltonian`, která je v podstatě seznam obsahující všechny požadované `FermionTerm` instance.</span><span class="sxs-lookup"><span data-stu-id="38da6-172">We may represent such Hamiltonians using the `FermionHamiltonian` class, which is essentially a list containing all the desired `FermionTerm` instances.</span></span>
<span data-ttu-id="38da6-173">Protože Hamiltonians jsou Hermitian podle definice, indexuje výrazy s použitím specializovaného typu `HermitianFermionTerm`, který také používá Hermitian symetrie při kontrole, zda jsou výrazy ekvivalentní.</span><span class="sxs-lookup"><span data-stu-id="38da6-173">As Hamiltonians are Hermitian by definition, we index terms using the more specialized type `HermitianFermionTerm` that also uses Hermitian symmetry when checking whether terms are equivalent.</span></span>

<span data-ttu-id="38da6-174">Můžeme vytvořit několik příkladů.</span><span class="sxs-lookup"><span data-stu-id="38da6-174">Let us construct a few illustrative examples.</span></span>
<span data-ttu-id="38da6-175">Vezměte v úvahu Hamiltonian $ \hat{H} = A_0 ^ \dagger A_1 + A_1 ^ \dagger A_0 $.</span><span class="sxs-lookup"><span data-stu-id="38da6-175">Consider the Hamiltonian $\hat{H} = a_0^\dagger a_1 + a_1^\dagger a_0$.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
<span data-ttu-id="38da6-176">Tuto konstrukci můžeme zjednodušit pomocí faktu, že operátory Hamiltonian jsou Hermitian operátory.</span><span class="sxs-lookup"><span data-stu-id="38da6-176">We may simplify this construction using the fact that Hamiltonian operators are Hermitian operators.</span></span>
<span data-ttu-id="38da6-177">Při přidávání podmínek do Hamiltonian pomocí `Add`se předpokládá, že jakýkoli neHermitian termín, jako je `fermionTerm0`, se spáruje s Hermitianem.</span><span class="sxs-lookup"><span data-stu-id="38da6-177">When adding terms to the Hamiltonian using `Add`, any non-Hermitian term such as `fermionTerm0` is assumed to be paired with its Hermitian conjugate.</span></span>
<span data-ttu-id="38da6-178">Proto následující fragment kódu představuje také stejný Hamiltonian:</span><span class="sxs-lookup"><span data-stu-id="38da6-178">Thus the following snippet also represents the same Hamiltonian:</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

<span data-ttu-id="38da6-179">Pomocí pravidel pro účely ochrany proti dojíždění některé instance `FermionTerm` ve skutečnosti odpovídají stejné sekvenci fermionic Operators, někdy až k znaménku minus.</span><span class="sxs-lookup"><span data-stu-id="38da6-179">Using the anti-commutation rules, some `FermionTerm` instances in the Hamiltonian actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="38da6-180">Zvažte například Hamiltonian $H = A_0 ^ \dagger A_1 ^ \dagger A_1 A_0-A_1 ^ \dagger A_0 ^ \dagger A_1 A_0 = 2a_0 ^ \dagger A_1 ^ \dagger A_1 A_0 $, což je součet výše uvedených podmínek.</span><span class="sxs-lookup"><span data-stu-id="38da6-180">For instance, consider the Hamiltonian $H=a_0^\dagger a_1^\dagger a_1 a_0 - a_1^\dagger a_0^\dagger a_1 a_0 =2a_0^\dagger a_1^\dagger a_1 a_0$, which is a sum of terms constructed above.</span></span>
<span data-ttu-id="38da6-181">Nemusí být vždy jasné pro uživatele, že se jedná o ekvivalentní výrazy, a proto je lze do Hamiltonian přidat samostatně.</span><span class="sxs-lookup"><span data-stu-id="38da6-181">It may not always be clear to the user that these are equivalent terms, and so they may be added to the Hamiltonian separately.</span></span>
<span data-ttu-id="38da6-182">Případně může být jedna z nich zajímat úpravu již existujících podmínek v Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="38da6-182">Alternatively, one may be interested in modifying already-existing terms in the Hamiltonian.</span></span>
<span data-ttu-id="38da6-183">V těchto případech můžeme kombinovat ekvivalentní výrazy následujícím způsobem.</span><span class="sxs-lookup"><span data-stu-id="38da6-183">In these cases, we may combine equivalent terms as follows.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
<span data-ttu-id="38da6-184">Kombinací koeficientů ekvivalentních podmínek snižujeme celkový počet podmínek v Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="38da6-184">By combining coefficients of equivalent terms, we reduce the total number of terms in the Hamiltonian.</span></span>
<span data-ttu-id="38da6-185">Později se tím sníží počet bran, které jsou potřeba k simulaci Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="38da6-185">Later on, this reduces the number of quantum gates required to simulate the Hamiltonian.</span></span>

### <a name="internal-representation"></a><span data-ttu-id="38da6-186">Interní reprezentace</span><span class="sxs-lookup"><span data-stu-id="38da6-186">Internal Representation</span></span>

<span data-ttu-id="38da6-187">Fermionic Hamiltonian s interakcemi jednoho a dvou částí je zastoupená v druhé-quantized zápisu jako</span><span class="sxs-lookup"><span data-stu-id="38da6-187">A fermionic Hamiltonian with one- and two-body interactions is represented in second-quantized notation as</span></span>

<span data-ttu-id="38da6-188">$ $ \begin{align} H = \sum\_{pq} H\_{pq} a ^ \dagger\_{p} a\_{q} + \frac{1}{2}\sum\_{pqrs} H\_{pqrs} a ^ \dagger\_{p} a ^ \dagger\_{q} @no__ t_10_ {r}\_{s}.</span><span class="sxs-lookup"><span data-stu-id="38da6-188">$$ \begin{align} H=\sum\_{pq}h\_{pq}a^\dagger\_{p}a\_{q}+\frac{1}{2}\sum\_{pqrs}h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}.</span></span>
<span data-ttu-id="38da6-189">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="38da6-189">\end{align} $$</span></span>

<span data-ttu-id="38da6-190">V tomto zápisu má maximálně $N ^ 2 + N ^ 4 $ hodnot.</span><span class="sxs-lookup"><span data-stu-id="38da6-190">In this notation, there are at most $N^2+N^4$ coefficients.</span></span>
<span data-ttu-id="38da6-191">Mnohé z těchto koeficientů však mohou být shromažďovány, protože odpovídají stejnému operátoru.</span><span class="sxs-lookup"><span data-stu-id="38da6-191">However, many of these coefficients may be collected as they correspond to the same operator.</span></span>
<span data-ttu-id="38da6-192">Například v případě, že $p, q, r, s $ jsou jedinečné indexy, můžeme použít pravidla pro boj do provozu k tomu, aby ukázala, že: $ $ a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r}\_{s} =-a ^ \dagger\_{q} a ^ \dagger\_{ p}\_{r}\_{s} =-a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{s}\_{r} = ^ \dagger\_{q} a ^ \dagger\_{p}\_{r}.</span><span class="sxs-lookup"><span data-stu-id="38da6-192">For instance, in the case where $p,q,r,s$ are distinct indices, we may use the anti-commutation rules to show that: $$ a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s} = -a^\dagger\_{q}a^\dagger\_{p}a\_{r}a\_{s} = -a^\dagger\_{p}a^\dagger\_{q}a\_{s}a\_{r} = a^\dagger\_{q}a^\dagger\_{p}a\_{s}a\_{r}.</span></span>
$$

<span data-ttu-id="38da6-193">Kromě toho, když je $H $ Hermitian, každý Hermitian fermionic operátor, řekněme $h\_{pqrs} a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} $, má Hermitian, který se nachází také v $H $.</span><span class="sxs-lookup"><span data-stu-id="38da6-193">Furthermore, as $H$ is Hermitian, every non-Hermitian fermionic operator, say $h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}$, has a Hermitian conjugate that is also found in $H$.</span></span> <span data-ttu-id="38da6-194">Aby bylo možné jedinečně indexovat skupiny podmínek, které jsou charakterizovány těmito symmetries, definujeme kanonické řazení pro indexy $ (i\_1, \cdots, i\_n, j\_1, \cdots, j\_m) $ z jakékoli sekvence $n + m $ fermionic Operators $a ^ \dagger\_{i\_1} \cdots a ^ \dagger\_{i\_n}\_{j\_1} \cdots a\_{j\_m} $as následující:</span><span class="sxs-lookup"><span data-stu-id="38da6-194">In order to uniquely index groups of terms characterized by these symmetries, we define a canonical ordering on the indices $(i\_1,\cdots,i\_n,j\_1,\cdots,j\_m)$ of any sequence of $n+m$ fermionic operators $a^\dagger\_{i\_1}\cdots a^\dagger\_{i\_n}a\_{j\_1}\cdots a\_{j\_m}$as follows:</span></span>
-   <span data-ttu-id="38da6-195">Všechny operátory vytváření $a ^ \dagger\_{i\_\cdot} $ jsou umístěné před všemi Annihilation operátory $a\_{j\_\cdot} $.</span><span class="sxs-lookup"><span data-stu-id="38da6-195">All creation operators $a^\dagger\_{i\_\cdot}$ are placed before all annihilation operators $a\_{j\_\cdot}$.</span></span>
-   <span data-ttu-id="38da6-196">Všechny indexy operátorů vytvoření jsou seřazené ve vzestupném pořadí, $i\_1 < i\_2 < <\_i n $.</span><span class="sxs-lookup"><span data-stu-id="38da6-196">All creation operator indices are sorted in ascending order, that is $i\_1< i\_2< \cdots < i\_n$.</span></span>
-   <span data-ttu-id="38da6-197">Všechny indexy operátorů Annihilation jsou seřazené v sestupném pořadí, což je $j\_1 > j\_2 \cdots > j\_m $.</span><span class="sxs-lookup"><span data-stu-id="38da6-197">All annihilation operator indices are sorted in descending order, that is $j\_1> j\_2 \cdots > j\_m$.</span></span>
-   <span data-ttu-id="38da6-198">Index nejvíce vlevo je menší nebo roven indexu, který je nejvíce vpravo, který je $i\_1 \ Le j\_m $.</span><span class="sxs-lookup"><span data-stu-id="38da6-198">The left-most index is less than or equal to the right-most index, that is $i\_1\le j\_m$.</span></span>

<span data-ttu-id="38da6-199">Sdělte nám tuto množinu kanonickě seřazených indexů jako $ $ \begin{align} (i\_1, \cdots, i\_n, j\_1, \cdots, j\_m) \in S\_{n, m}.</span><span class="sxs-lookup"><span data-stu-id="38da6-199">Let us identify this set of canonically ordered indices as $$ \begin{align} (i\_1,\cdots,i\_n,j\_1,\cdots,j\_m) \in S\_{n,m}.</span></span>
<span data-ttu-id="38da6-200">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="38da6-200">\end{align} $$</span></span>

<span data-ttu-id="38da6-201">V tomto kanonickém řazení může být fermionic Hamiltonian vyjádřena jako $ $ \begin{align} H = \sum\_{(p, q) \in S\_{1,1}} H '\_{pq} \frac{a ^ \dagger\_{p}\_{q} + a ^ \dagger\_{q}\_p}}{2}+ \sum\_{(p, q, r, s) \in S\_{2,2}} h '\_{pqrs} \frac{a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r}\_{s} + a ^ \dagger\_{s} a ^ \ Dagger\_{r}\_{q} a\_{p}}{2}, \end{align} $ $ s vhodně přizpůsobeným jedním a dvěma e-integrály $h\_{pq} $ a $h\_{pqrs} $ v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="38da6-201">With this canonical ordering, the fermionic Hamiltonian may be expressed as $$ \begin{align} H=\sum\_{(p,q)\in S\_{1,1}}h'\_{pq}\frac{a^\dagger\_{p}a\_{q}+a^\dagger\_{q}a\_{p}}{2}+\sum\_{(p,q,r,s)\in S\_{2,2}}h'\_{pqrs}\frac{a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}+a^\dagger\_{s}a^\dagger\_{r}a\_{q}a\_{p}}{2}, \end{align} $$ with suitably adapted one- and two-electron integrals $h'\_{pq}$ and $h'\_{pqrs}$, respectively.</span></span>
