---
title: Simulace Hamiltonian Dynamics | Microsoft Docs
description: Simulace koncepčních dokumentů Hamiltonian Dynamics
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 4d1924386eadb427e8f53bc0a177453a341f185f
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864453"
---
# <a name="simulating-hamiltonian-dynamics"></a><span data-ttu-id="a0913-103">Simulace Hamiltonian Dynamics</span><span class="sxs-lookup"><span data-stu-id="a0913-103">Simulating Hamiltonian Dynamics</span></span>

<span data-ttu-id="a0913-104">Jakmile se Hamiltonian vyjádří jako součet základních operátorů, může se dynamika kompilovat do základních operací brány pomocí hostitele známých technik.</span><span class="sxs-lookup"><span data-stu-id="a0913-104">Once the Hamiltonian has been expressed as a sum of elementary operators the dynamics can then be compiled into fundamental gate operations using a host of well-known techniques.</span></span>
<span data-ttu-id="a0913-105">Mezi tři efektivní přístupy patří Trotter – vzorce Suzuki, lineární kombinace unitaries a qubitization.</span><span class="sxs-lookup"><span data-stu-id="a0913-105">Three efficient approaches include are Trotter–Suzuki formulas, linear combinations of unitaries, and qubitization.</span></span>
<span data-ttu-id="a0913-106">Tyto tři níže uvedené postupy uvádíme níže a poskytnou konkrétní příklady Q #, jak implementovat tyto metody pomocí knihovny simulace Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="a0913-106">We explain these three approaches below and give concrete Q# examples of how to implement these methods using the Hamiltonian simulation library.</span></span>


## <a name="trottersuzuki-formulas"></a><span data-ttu-id="a0913-107">Trotter – vzorce Suzuki</span><span class="sxs-lookup"><span data-stu-id="a0913-107">Trotter–Suzuki Formulas</span></span>
<span data-ttu-id="a0913-108">Vzorec na pozadí Trotter – vzorce Suzuki jsou jednoduché: vyjádřete Hamiltonian jako součet jednoduchého simulace Hamiltonians a pak přibližný celkový vývoj jako sekvence těchto jednodušších vývojů.</span><span class="sxs-lookup"><span data-stu-id="a0913-108">The idea behind Trotter–Suzuki formulas is simple: express the Hamiltonian as a sum of easy to simulate Hamiltonians and then approximate the total evolution as a sequence of these simpler evolutions.</span></span>
<span data-ttu-id="a0913-109">Konkrétně dejte $H = \ sum_ {j = 1} ^ m H_j $ být Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="a0913-109">In particular, let $H=\sum_{j=1}^m H_j$ be the Hamiltonian.</span></span>
<span data-ttu-id="a0913-110">Pak $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $ to znamená, že pokud $t \ll $1, bude chyba v této aproximaci zanedbatelná.</span><span class="sxs-lookup"><span data-stu-id="a0913-110">Then, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O(m^2 t^2), $$ which is to say that, if $t\ll 1$, then the error in this approximation becomes negligible.</span></span>
<span data-ttu-id="a0913-111">Všimněte si, že pokud $e ^ {-i H} $ byly normální exponenciální, chyba v této aproximaci nebude $O (m ^ 2 t ^ 2) $: by to bylo nula.</span><span class="sxs-lookup"><span data-stu-id="a0913-111">Note that if $e^{-i H t}$ were an ordinary exponential then the error in this approximation would not be $O(m^2 t^2)$: it would be zero.</span></span>
<span data-ttu-id="a0913-112">K této chybě dochází, protože $e ^ {-iHt} $ je exponenciální exponenciální a v důsledku toho dojde k chybě při použití tohoto vzorce z důvodu faktu, že $H _J $ podmínka neprobíhá po dojíždění (*tj.* $H _J H_k \Ne H_k H_j $ všeobecně).</span><span class="sxs-lookup"><span data-stu-id="a0913-112">This error occurs because $e^{-iHt}$ is an operator exponential and as a result there is an error incurred when using this formula due to the fact that the $H_j$ terms do not commute (*i.e.*, $H_j H_k \ne H_k H_j$ in general).</span></span>

<span data-ttu-id="a0913-113">Pokud je $t $ velké, Trotter vzorce Suzuki se dají použít k tomu, aby se tento dynamika přesně simulovaly tím, že se rozbalí do sekvence krátkého časového intervalu.</span><span class="sxs-lookup"><span data-stu-id="a0913-113">If $t$ is large, Trotter–Suzuki formulas can still be used to simulate the dynamics accurately by breaking it up into a sequence of short time-steps.</span></span>
<span data-ttu-id="a0913-114">Nechť $r $ je počet kroků provedených v čase vývoje.</span><span class="sxs-lookup"><span data-stu-id="a0913-114">Let $r$ be the number of steps taken in the time evolution.</span></span>
<span data-ttu-id="a0913-115">Potom máme $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ Right) ^ r + O (m ^ 2 t ^ 2/r), $ $ to znamená, že pokud se $r $ škáluje jako $m ^ 2 t ^ 2/\ Epsilon $, může být chyba vytvořená maximálně $ \epsilon $ pro všechny $ \epsilon > 0 $.</span><span class="sxs-lookup"><span data-stu-id="a0913-115">Then, we have that $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\right)^r + O(m^2 t^2/r), $$ which implies that if $r$ scales as $m^2 t^2/\epsilon$ then the error can be made at most $\epsilon$ for any $\epsilon>0$.</span></span>

<span data-ttu-id="a0913-116">Přesnější sblížení lze sestavit pomocí sekvence exponenciálních exponenciálních operátorů, aby se chybové výrazy zrušily.</span><span class="sxs-lookup"><span data-stu-id="a0913-116">More accurate approximations can be built by constructing a sequence of operator exponentials such that the error terms cancel.</span></span>
<span data-ttu-id="a0913-117">Nejjednodušším takový vzorec, symetrický vzorec Trotter nebo rozdělení Strang, má formu $ $ U_1 (t) = \ prod_ {j = 1} ^ m e ^ {-iH_j t/2} \ prod_ {j = m} ^ 1 e ^ {-iH_j t} = e ^ {-iHt} + O (m ^ 3 t ^ 3), $ $ může být menší než $ \epsilon $ pro jakékoli $ \epsilon > 0 $ tak, že vyberete $r $ pro škálování jako $m ^ {3/2} t ^ {3/2}/\sqrt {\ Epsilon} $.</span><span class="sxs-lookup"><span data-stu-id="a0913-117">The simplest such formula, the symmetric Trotter formula or Strang splitting, takes the form $$ U_1(t) =\prod_{j=1}^m e^{-iH_j t/2}\prod_{j=m}^1 e^{-iH_j t} = e^{-iHt} + O(m^3 t^3), $$ which can be made less than $\epsilon$ for any $\epsilon>0$ by choosing $r$ to scale as $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.</span></span>

<span data-ttu-id="a0913-118">I vyšší pořadí vzorců Trotter lze vytvořit na základě $U _1 $.</span><span class="sxs-lookup"><span data-stu-id="a0913-118">Even higher-order Trotter formulas can be constructed based on $U_1$.</span></span>
<span data-ttu-id="a0913-119">Nejjednodušší je následující vzorec čtvrté objednávky, původně představeno pomocí Suzuki: $ $ U_2 (t) = U_1 ^ 2 (s_1t) U_1 ([1-4s_1] t) U_1 ^ 2 (s_1 t) = e ^ {-iHt} + O (m ^ 5t ^ 5), $ $ kde $s _1 = (4-4 ^ {1/3}) ^{-1}$.</span><span class="sxs-lookup"><span data-stu-id="a0913-119">The simplest is the following fourth order formula, originally introduced by Suzuki: $$ U_2(t) = U_1^2(s_1t) U_1([1-4s_1]t)U_1^2(s_1 t) = e^{-iHt} +O(m^5t^5), $$ where $s_1 = (4-4^{1/3})^{-1}$.</span></span>
<span data-ttu-id="a0913-120">Obecně platí, že je možné podobně vytvořit libovolně vyšší pořadí vzorců; Nicméně náklady vyplývající z použití složitějších integrátorů často převažují nad rámec čtvrtého řádu pro většinu praktických problémů.</span><span class="sxs-lookup"><span data-stu-id="a0913-120">In general, arbitrarily high-order formulas can be similarly constructed; however, the costs incurred from using more complex integrators often outweigh the benefits beyond fourth order for most practical problems.</span></span>

<span data-ttu-id="a0913-121">Aby výše uvedené strategie fungovaly, potřebujeme metodu pro simulaci třídy typu "$e ^ {-iH_j t} $".</span><span class="sxs-lookup"><span data-stu-id="a0913-121">In order to make the above strategies work, we need to have a method for simulating a wide class of $e^{-iH_j t}$.</span></span>
<span data-ttu-id="a0913-122">Nejjednodušší rodina Hamiltonians a pravděpodobně je nejužitečnější, kterou bychom mohli použít tady jsou Pauli operátory.</span><span class="sxs-lookup"><span data-stu-id="a0913-122">The simplest family of Hamiltonians, and arguably most useful, that we could use here are Pauli operators.</span></span>
<span data-ttu-id="a0913-123">Operátory Pauli je možné snadno simulovat, protože je možné je diagonální pomocí operací Clifford (což jsou standardní brány ve výpočetním prostředí).</span><span class="sxs-lookup"><span data-stu-id="a0913-123">Pauli operators can be easily simulated because they can be diagonalized using Clifford operations (which are standard gates in quantum computing).</span></span>
<span data-ttu-id="a0913-124">Po jejich objasnění můžete jejich eigenvalues najít vynásobením parity qubits, na které jednají.</span><span class="sxs-lookup"><span data-stu-id="a0913-124">Further, once they have been diagonalized, their eigenvalues can be found by computing the parity of the qubits on which they act.</span></span>

<span data-ttu-id="a0913-125">Například $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ WHERE $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-IT} & 0 & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="a0913-125">For example, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ where $$ e^{-i Z \otimes Z t} = \begin{bmatrix} e^{-it} & 0  & 0  & 0 </span></span>\\\
        <span data-ttu-id="a0913-126">0 & e ^ {i t} & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="a0913-126">0 & e^{i t}  & 0 & 0 </span></span>\\\
        <span data-ttu-id="a0913-127">0 & 0 & e ^ {IT} & 0 </span><span class="sxs-lookup"><span data-stu-id="a0913-127">0 & 0 & e^{it} & 0 </span></span>\\\
        <span data-ttu-id="a0913-128">0 & 0 & 0 & e ^ {-IT} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="a0913-128">0 & 0 & 0 & e^{-it} \end{bmatrix}.</span></span>
<span data-ttu-id="a0913-129">$ $ Sem $e ^ {-iHt} \ket{00} = e ^ {IT}{00}\ket a $e ^ {-iHt} \ket{01} = e ^ {-IT} \ket{01}$, které se dá vidět přímo jako důsledek faktu, že parita $0 $ je $0 $, zatímco parita bitového řetězce $1 $ je $1 $.</span><span class="sxs-lookup"><span data-stu-id="a0913-129">$$ Here, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ and $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, which can be seen directly as a consequence of the fact that the parity of $00$ is $0$ while the parity of the bit string $01$ is $1$.</span></span>

<span data-ttu-id="a0913-130">Exponenciální operátory operátorů Pauli lze implementovat přímo do Q # pomocí operace <xref:microsoft.quantum.primitive.exp>:</span><span class="sxs-lookup"><span data-stu-id="a0913-130">Exponentials of Pauli operators can be implemented directly in Q# using the <xref:microsoft.quantum.primitive.exp> operation:</span></span>
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies e^{- i X \otimes X t} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

<span data-ttu-id="a0913-131">Pro Fermionic Hamiltonians, [Wigner (Jordánsko – rekompozici](xref:microsoft.quantum.chemistry.concepts.jordanwigner) ), vhodně namapuje Hamiltonian na součet Paulich operátorů.</span><span class="sxs-lookup"><span data-stu-id="a0913-131">For Fermionic Hamiltonians, the [Jordan–Wigner decomposition](xref:microsoft.quantum.chemistry.concepts.jordanwigner) conveniently maps the Hamiltonian into a sum of Pauli operators.</span></span>
<span data-ttu-id="a0913-132">To znamená, že výše uvedený přístup lze snadno přizpůsobit simulaci chemie.</span><span class="sxs-lookup"><span data-stu-id="a0913-132">This means that the above approach can easily be adapted to simulating chemistry.</span></span>
<span data-ttu-id="a0913-133">Místo ručního přeskočíní všech Pauli podmínek ve formě Jordánska-Wigner představuje jednoduchý příklad, jak může tato simulace v rámci chemického zpracování vypadat.</span><span class="sxs-lookup"><span data-stu-id="a0913-133">Rather than manually looping over all Pauli terms in the Jordan-Wigner representation, below is a simple example of how executing such a simulation within the chemistry would look.</span></span>
<span data-ttu-id="a0913-134">Náš výchozí bod je [Jordánsko – Wigner kódování](xref:microsoft.quantum.chemistry.concepts.jordanwigner) Fermionic Hamiltonian, vyjádřené v kódu jako instance třídy `JordanWignerEncoding`.</span><span class="sxs-lookup"><span data-stu-id="a0913-134">Our starting point is a [Jordan–Wigner encoding](xref:microsoft.quantum.chemistry.concepts.jordanwigner) of the Fermionic Hamiltonian, expressed in code as an instance of the `JordanWignerEncoding` class.</span></span>

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

<span data-ttu-id="a0913-135">Tento formát Jordánska – Wigner reprezentace, kterou jsou spotřebními algoritmy Q #, je uživatelsky definovaný typ `JordanWignerEncodingData`.</span><span class="sxs-lookup"><span data-stu-id="a0913-135">This format of the Jordan–Wigner representation that is consumable by the Q# simulation algorithms is a user-defined type `JordanWignerEncodingData`.</span></span>
<span data-ttu-id="a0913-136">V rámci Q # se tento formát předává do funkce usnadnění `TrotterStepOracle`, která vrací operátor přibližného vývoje času pomocí Trotter – integrátor Suzuki, kromě dalších parametrů požadovaných pro jeho spuštění.</span><span class="sxs-lookup"><span data-stu-id="a0913-136">Within Q#, this format is passed to a convenience function `TrotterStepOracle` that returns an operator approximating time-evolution using the Trotter—Suzuki integrator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="a0913-137">Důležité: Tato implementace používá několik optimalizací popsaných v [simulaci elektronické struktury Hamiltonians s využitím počítačů](https://arxiv.org/abs/1001.3855) s více procesory a [vylepšením](https://arxiv.org/abs/1403.1539) procesorových procesorů pro účely minimalizace počtu požadovaných rotací s jedním qubit, jakož i k omezení chyb simulace.</span><span class="sxs-lookup"><span data-stu-id="a0913-137">Importantly, this implementation applies some optimizations discussed in [Simulation of Electronic Structure Hamiltonians Using Quantum Computers](https://arxiv.org/abs/1001.3855) and [Improving Quantum Algorithms for Quantum Chemistry](https://arxiv.org/abs/1403.1539) to minimize the number of single-qubit rotations required, as well as reduce simulation errors.</span></span>

## <a name="qubitization"></a><span data-ttu-id="a0913-138">Qubitization</span><span class="sxs-lookup"><span data-stu-id="a0913-138">Qubitization</span></span>

<span data-ttu-id="a0913-139">Qubitization je alternativním přístupem k simulaci, která využívá nápady z kroků pro simulaci dynamiky.</span><span class="sxs-lookup"><span data-stu-id="a0913-139">Qubitization is an alternative approach to simulation that uses ideas from quantum walks to simulate quantum dynamics.</span></span>
<span data-ttu-id="a0913-140">I když qubitization vyžaduje více qubits než Trotter vzorce, metoda příslibů optimální škálování s časem vývoje a odolností proti chybám.</span><span class="sxs-lookup"><span data-stu-id="a0913-140">While qubitization requires more qubits than Trotter formulas, the method promises optimal scaling with the evolution time and the error tolerance.</span></span>
<span data-ttu-id="a0913-141">Z těchto důvodů se stala přizpůsobenou metodou pro simulaci Hamiltonian Dynamics v obecném a pro řešení potíží s elektronickými strukturami, konkrétně.</span><span class="sxs-lookup"><span data-stu-id="a0913-141">For these reasons it has become a favored method for simulating Hamiltonian dynamics in general, and for solving the electronic structure problem in particular.</span></span>

<span data-ttu-id="a0913-142">Na vysoké úrovni to qubitization provádí pomocí následujících kroků.</span><span class="sxs-lookup"><span data-stu-id="a0913-142">At a high level, qubitization accomplishes this through the following steps.</span></span>
<span data-ttu-id="a0913-143">Nejdřív dejte $H = \ sum_j h_j H_j $ pro jednotkové a Hermitian $H _J $ a $h _j \ge $0.</span><span class="sxs-lookup"><span data-stu-id="a0913-143">First, let $H=\sum_j h_j H_j$ for unitary and Hermitian $H_j$ and $h_j\ge 0$.</span></span>
<span data-ttu-id="a0913-144">Provedením dvojice odrazů qubitization implementuje operátor, který je ekvivalentní $ $W = e ^ {\Pm i \cos ^{-1}(H/| H | _1)}, $ $ WHERE $ | H | _1 = \ sum_j | h_j | $.</span><span class="sxs-lookup"><span data-stu-id="a0913-144">By performing a pair of reflections, qubitization implements an operator that is equivalent to $$W=e^{\pm i \cos^{-1}(H/|h|_1)},$$ where $|h|_1 = \sum_j |h_j|$.</span></span>
<span data-ttu-id="a0913-145">Další krok zahrnuje transformaci eigenvalues operátoru průchodu z $e ^ {i\pm \cos ^{-1}(E_k/| h | _1)} $, kde $E _k $ jsou eigenvalues $H $ to $e ^ {-iE_k t} $.</span><span class="sxs-lookup"><span data-stu-id="a0913-145">The next step involves transforming the eigenvalues of the walk operator from $e^{i\pm \cos^{-1}(E_k/|h|_1)}$, where $E_k$ are the eigenvalues of $H$ to $e^{-iE_k t}$.</span></span>
<span data-ttu-id="a0913-146">To je možné dosáhnout použitím celé řady metod transformace hodnot v jednotném provozu, včetně [zpracování signálu](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span><span class="sxs-lookup"><span data-stu-id="a0913-146">This can be achieved using a variety of quantum singular value transformation methods including [quantum signal processing](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span></span>

<span data-ttu-id="a0913-147">Případně, pokud jsou požadována pouze statická množství (například stavová energie Hamiltonian), pak bude stačit použít [odhad fáze](xref:microsoft.quantum.libraries.characterization) přímo na $W $ k odhadu energetické energie z výsledku pomocí kosinus výsledku.</span><span class="sxs-lookup"><span data-stu-id="a0913-147">Alternatively, if only static quantities are desired (such as the ground state energy of the Hamiltonian) then it suffices to apply [phase estimation](xref:microsoft.quantum.libraries.characterization) directly to $W$ to estimate the ground state energy from the result by taking the cosine of the result.</span></span>
<span data-ttu-id="a0913-148">To je důležité, protože umožňuje, aby se spektrální transformace prováděla klasickým způsobem namísto použití metody transformace hodnot na základě základu hodnoty.</span><span class="sxs-lookup"><span data-stu-id="a0913-148">This is significant because it allows the spectral transformation to be performed classically rather than using a quantum singular value transformation method.</span></span>

<span data-ttu-id="a0913-149">Na podrobnější úrovni implementace qubitization vyžaduje dvě podrutiny, které poskytují rozhraní pro Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="a0913-149">On a more detailed level, the implementation of qubitization requires two subroutines that provide the interfaces for the Hamiltonian.</span></span>
<span data-ttu-id="a0913-150">Na rozdíl od metod Trotter – Suzuki jsou tyto podrutiny bez klasických procesorů a jejich implementace bude vyžadovat použití logarithmically více qubits, než by bylo nutné pro simulaci založenou na Trotter.</span><span class="sxs-lookup"><span data-stu-id="a0913-150">Unlike Trotter–Suzuki methods, these subroutines are quantum not classical and their implementation will necessitate using logarithmically more qubits than would be required for a Trotter-based simulation.</span></span>

<span data-ttu-id="a0913-151">První podprogram počátečních operací, který qubitization používá, se nazývá $ \operatorname{Select} $ a je přislíbena, aby \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{Equation} kde každý $H _j $ se předpokládá jako Hermitian a jednotná.</span><span class="sxs-lookup"><span data-stu-id="a0913-151">The first quantum subroutine that qubitization uses is called $\operatorname{Select}$ and it is promised to yield \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} where each $H_j$ is assumed to be Hermitian and unitary.</span></span>
<span data-ttu-id="a0913-152">I když se to může zdát být omezující, odvolat, že Pauli operátory jsou Hermitian a jednotná, takže aplikace, jako je například, nespadají do této architektury přirozeně.</span><span class="sxs-lookup"><span data-stu-id="a0913-152">While this may seem to be restrictive, recall that Pauli operators are Hermitian and unitary and so applications like quantum chemistry simulation naturally fall into this framework.</span></span>
<span data-ttu-id="a0913-153">Operace $ \operatorname{Select} $, třeba překvapivě, je ve skutečnosti operace reflexe.</span><span class="sxs-lookup"><span data-stu-id="a0913-153">The $\operatorname{Select}$ operation, perhaps surprisingly, is actually a reflection operation.</span></span>
<span data-ttu-id="a0913-154">To může být patrné ze skutečnosti, že $ \operatorname{Select} ^ 2 \ KET {j} \ket{\psi} = \ket{j} \ket{\psi} $, protože každá $H _j $ je jednotná a Hermitian a má tedy eigenvalues $ \Pm $1.</span><span class="sxs-lookup"><span data-stu-id="a0913-154">This can be seen from the fact that $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} \ket{\psi}$ since each $H_j$ is unitary and Hermitian and thus has eigenvalues $\pm 1$.</span></span>

<span data-ttu-id="a0913-155">Druhá podrutina se nazývá $ \operatorname{Prepare} $.</span><span class="sxs-lookup"><span data-stu-id="a0913-155">The second subroutine is called $\operatorname{Prepare}$.</span></span>
<span data-ttu-id="a0913-156">Zatímco operace Select poskytuje prostředky pro soudržný přístup ke každému Hamiltonian podmínkám $H _j $ přípravná subrutina poskytuje metodu pro přístup k koeficientům $h _j $, \begin{Equation} \operatorname{Prepare}\ket{0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="a0913-156">While the select operation provides a means to coherently access each of the Hamiltonian terms $H_j$ the prepare subroutine gives a method for accessing the coefficients $h_j$, \begin{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{|h|_1}}\ket{j}.</span></span>
<span data-ttu-id="a0913-157">\end{Equation} se pak pomocí brány řízených fází vynásobení zobrazuje $ $ \Lambda\ket{0}^ {\otimes n} = \begin{Cases} \-\ket{x} & \Text{if} x = 0 </span><span class="sxs-lookup"><span data-stu-id="a0913-157">\end{equation} Then, by using a multiply controlled phase gate, we see that $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 </span></span>\\\
        <span data-ttu-id="a0913-158">\ket{x} & \Text{Otherwise} \end{Cases}.</span><span class="sxs-lookup"><span data-stu-id="a0913-158">\ket{x}   & \text{otherwise} \end{cases}.</span></span>
$$

<span data-ttu-id="a0913-159">Operace $ \operatorname{Prepare} $ se nepoužívá přímo v qubitization, ale místo toho se používá k implementaci reflexe o stavu, který $ \operatorname{Prepare} $ vytvoří $ $ \begin{align} R &amp; = 1-2 \ operátor {Prepare} \ket{0}\bra{0} \operatorname{Prepare} ^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^{-1}.</span><span class="sxs-lookup"><span data-stu-id="a0913-159">The $\operatorname{Prepare}$ operation is not used directly in qubitization, but rather is used to implement a reflection about the state that $\operatorname{Prepare}$ creates $$ \begin{align} R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare}^{-1}.</span></span>
<span data-ttu-id="a0913-160">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a0913-160">\end{align} $$</span></span>

<span data-ttu-id="a0913-161">Operátor průchodu $W $, může být vyjádřen v souvislosti s $ \operatorname{Select} $ a $R $ Operations jako $ $ W = \operatorname{Select} R, $ $, které se znovu dají použít k implementaci operátoru, který je ekvivalentní (až do Isometry), do $e ^ {\Pm i \cos ^{-1}(H/| H | _1)} $.</span><span class="sxs-lookup"><span data-stu-id="a0913-161">The walk operator, $W$, can be expressed in terms of the $\operatorname{Select}$ and $R$ operations as $$ W = \operatorname{Select} R, $$ which again can be seen to implement an operator that is equivalent (up to an isometry) to $e^{\pm i \cos^{-1}(H/|h|_1)}$.</span></span>

<span data-ttu-id="a0913-162">Tyto podrutiny se dají snadno nastavit v Q #.</span><span class="sxs-lookup"><span data-stu-id="a0913-162">These subroutines are easy to set up in Q#.</span></span>
<span data-ttu-id="a0913-163">Zvažte například jednoduché qubit příčné Ising Hamiltonian, kde $H = X_1 + X_2 + Z_1 Z_2 $.</span><span class="sxs-lookup"><span data-stu-id="a0913-163">As an example, consider the simple qubit transverse-Ising Hamiltonian where $H = X_1 + X_2 + Z_1 Z_2$.</span></span>
<span data-ttu-id="a0913-164">V tomto případě je možné pomocí <xref:microsoft.quantum.canon.multiplexoperations>vyvolat kód Q #, který by implementoval operaci $ \operatorname{Select} $, zatímco operaci $ \operatorname{Prepare} $ lze implementovat pomocí <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span><span class="sxs-lookup"><span data-stu-id="a0913-164">In this case, Q# code that would implement the $\operatorname{Select}$ operation is invoked by <xref:microsoft.quantum.canon.multiplexoperations>, whereas the $\operatorname{Prepare}$ operation can be implemented using <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span></span>
<span data-ttu-id="a0913-165">Příklad, který zahrnuje simulaci modelu Hubbard, najdete jako [ukázku Q](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).</span><span class="sxs-lookup"><span data-stu-id="a0913-165">An example that involves simulating the Hubbard model can be found as a [Q# sample](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).</span></span>

<span data-ttu-id="a0913-166">Ruční určení těchto kroků pro jakékoli problémy chemického složení by vyžadovalo mnohem úsilí, které se vyhne použití knihovny složení.</span><span class="sxs-lookup"><span data-stu-id="a0913-166">Manually specifying these steps for arbitrary chemistry problems would require much effort, which is avoided using the chemistry library.</span></span>
<span data-ttu-id="a0913-167">Podobně jako u algoritmu simulace Trotter-Suzuki výše se `JordanWignerEncodingData` předává do funkce usnadnění `QubitizationOracle`, která vrací operátor Pass-kromě dalších parametrů požadovaných pro jeho spuštění.</span><span class="sxs-lookup"><span data-stu-id="a0913-167">Similarly to the Trotter–Suzuki simulation algorithm above, the `JordanWignerEncodingData` is passed to the convenience function `QubitizationOracle` that returns the walk-operator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="a0913-168">V důležitém případě je implementace <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> platná pro libovolný Hamiltonians zadaný jako lineární kombinaci řetězců Pauli.</span><span class="sxs-lookup"><span data-stu-id="a0913-168">Importantly, the implementation <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> is applicable to arbitrary Hamiltonians specified as a linear combination of Pauli strings.</span></span>
<span data-ttu-id="a0913-169">Verze, která je optimalizována pro chemické simulace, je vyvolána pomocí <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span><span class="sxs-lookup"><span data-stu-id="a0913-169">A version optimized for chemistry simulations is invoked using <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span></span>
<span data-ttu-id="a0913-170">Tato verze je optimalizovaná tak, aby minimalizovala počet bran T, které využívají techniky popsané v tématu [kódování elektronických spektra v okruhech s lineárním T](https://arxiv.org/abs/1805.03662).</span><span class="sxs-lookup"><span data-stu-id="a0913-170">This version is optimized to minimize the number of T gates using techniques discussed in [Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity](https://arxiv.org/abs/1805.03662).</span></span>
