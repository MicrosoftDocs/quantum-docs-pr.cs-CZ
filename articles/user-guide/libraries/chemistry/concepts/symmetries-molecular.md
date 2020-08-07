---
title: Symmetries molekulových integrálů
description: Přečtěte si o použití Q# typu OrbitalIntegral k zobrazení výčtu molekulových symmetries.
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1f71c0ac8e2cd2781c0bc7b23d6c9222f3b9d18a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869439"
---
# <a name="symmetries-of-molecular-integrals"></a><span data-ttu-id="21ba9-103">Symmetries molekulových integrálů</span><span class="sxs-lookup"><span data-stu-id="21ba9-103">Symmetries of Molecular Integrals</span></span>

<span data-ttu-id="21ba9-104">Podstata symetrie Coulomb Hamiltonian, která je Hamiltonian v [modelech pro práci s elektronickými systémy](xref:microsoft.quantum.chemistry.concepts.quantummodels), která popisuje Electrons interakci elektricky navzájem a s Nuclei, vede k tomu, že je možné využít řadu symmetries, které lze zneužít ke komprimaci podmínek v Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="21ba9-104">The inherent symmetry of the Coulomb Hamiltonian, which is the Hamiltonian given in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels), that describes electrons interacting electrically with each other and with the nuclei, leads to a number of symmetries that can be exploited to compress the terms in the Hamiltonian.</span></span>
<span data-ttu-id="21ba9-105">Obecně platí, že pokud se neprovádí žádné další předpoklady pro základní funkce $ \ psi_j $, máme jenom tento \begin{Equation} h_ {pqrs} = h_ {QPSR}. \tag{★} \label{EQ: hpqrs} \end{Equation}, který se dá hned zobrazit z integrálních prvků v [modelech nečinnosti u elektronických systémů](xref:microsoft.quantum.chemistry.concepts.quantummodels) , když se Poklade, že jejich hodnoty zůstávají stejné, pokud se $p, q $ a $r, s $ mění z ochrany po rozjíždění.</span><span class="sxs-lookup"><span data-stu-id="21ba9-105">In general if no further assumptions are made about the basis functions $\psi_j$ then we only have that \begin{equation} h_{pqrs}= h_{qpsr},\tag{★}\label{eq:hpqrs} \end{equation} which can be immediately seen from the integrals in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) upon noting that their values remain identical if $p,q$ and $r,s$ are interchanged from anti-commutation.</span></span>

<span data-ttu-id="21ba9-106">Pokud předpokládáme, že orbitals jsou reálné (stejně jako pro Gaussovské orbitalé základny), budeme dál mít k dispozici \begin{Equation} h_ {pqrs} = h_ {QPSR} = h_ {srqp} = h_ {rspq} = h_ {rqps} = H_ {psrq} = h_ {SPQR} = h_ {qrsp} .\tag {★} \label{EQ: hpqrsreal} \end{Equation}, které tyto předpoklady obsahují, můžeme použít výše uvedené symmetries k omezení dat potřebných k uložení prvků matrice Hamiltonian o faktoru $8 $; i když tomu tak je, umožňuje importovat data konzistentním způsobem, který je trochu náročnější.</span><span class="sxs-lookup"><span data-stu-id="21ba9-106">If we assume that the spin-orbitals are real-valued (as they are for Gaussian orbital bases) then we further have that \begin{equation} h_{pqrs} = h_{qpsr} = h_{srqp} = h_{rspq}=h_{rqps}=h_{psrq}=h_{spqr}=h_{qrsp}.\tag{★}\label{eq:hpqrsreal} \end{equation} Given such assumptions hold, we can use the above symmetries to reduce the data needed to store the matrix elements of the Hamiltonian by a factor of $8$; although doing so makes importing data in a consistent way slightly more challenging.</span></span>
<span data-ttu-id="21ba9-107">Knihovna simulace Hamiltonian má podrutiny, které lze použít k importu integrálních souborů buď z [LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) , nebo přímo z [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span><span class="sxs-lookup"><span data-stu-id="21ba9-107">Fortunately the Hamiltonian simulation library has subroutines that can be used to import integral files from either [LIQUI$|\rangle$](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) or directly from [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span></span>

<span data-ttu-id="21ba9-108">Molekulové Orbital integrály (tj. $h \_ {pq} $ a $h \_ {pqrs} $), jako jsou reprezentovány pomocí `OrbitalIntegral` typu, který poskytuje řadu užitečných funkcí pro vyjádření této symetrie.</span><span class="sxs-lookup"><span data-stu-id="21ba9-108">Molecular orbital integrals (i.e. the $h\_{pq}$ and $h\_{pqrs}$ terms) such as these are represented using the `OrbitalIntegral` type, which provides a number of helpful functions to express this symmetry.</span></span>
```csharp
    // Load the namespace containing orbital integral objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // Create a `OrbitalIntegral` instance to store a one-electron molecular 
    // orbital integral data.
    var oneElectronOrbitalIndices = new[] { 0, 1 };
    var oneElectronCoefficient = 1.0;
    var oneElectronIntegral = new OrbitalIntegral(oneElectronOrbitalIndices, oneElectronCoefficient);

    // This enumerates all one-electron integrals with the same coefficient --
    // an array of equivalent `OrbitalIntegral` instances is generated. In this
    // case, there are two elements.
    var oneElectronIntegrals = oneElectronIntegral.EnumerateOrbitalSymmetries();

    // Create a `OrbitalIntegral` instance to store a two-electron molecular orbital integral data.
    var twoElectronOrbitalIndices = new[] { 0, 1, 2, 3 };
    var twoElectronCoefficient = 0.123;
    var twoElectronIntegral = new OrbitalIntegral(twoElectronOrbitalIndices, twoElectronCoefficient);

    // This enumerates all two-electron integrals with the same coefficient -- 
    // an array of equivalent `OrbitalIntegral` instances is generated. In 
    // this case, there are 8 elements.
    var twoElectronIntegrals = twoElectronIntegral.EnumerateOrbitalSymmetries();
```

<span data-ttu-id="21ba9-109">Kromě výčtu všech Orbital integrálů, které jsou číselně identické, je možné vygenerovat seznam všech Orbital indexů obsažených v Hamiltonian reprezentovaných pomocí `OrbitalIntegral` .</span><span class="sxs-lookup"><span data-stu-id="21ba9-109">In addition to enumerating over all orbital integrals that are numerically identical, a list of all spin-orbital indices contained in the Hamiltonian represented by an `OrbitalIntegral` may be generated as follows.</span></span>
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a><span data-ttu-id="21ba9-110">Sestavování Fermionic Hamiltonians z molekulových integrálů</span><span class="sxs-lookup"><span data-stu-id="21ba9-110">Constructing Fermionic Hamiltonians from Molecular Integrals</span></span>

<span data-ttu-id="21ba9-111">Namísto sestavování Fermionic Hamiltonian přidáním `FermionTerm` s můžete automaticky přidat všechny příslušné výrazy, které odpovídají jednotlivým Orbital integrálu.</span><span class="sxs-lookup"><span data-stu-id="21ba9-111">Rather than constructing a Fermionic Hamiltonian by adding `FermionTerm`s, all terms corresponding to each orbital integral may be added automatically.</span></span>
<span data-ttu-id="21ba9-112">Například následující kód automaticky vytvoří výčet pro všechny permutace symmetries a vyřadí výrazy v kanonickém pořadí:</span><span class="sxs-lookup"><span data-stu-id="21ba9-112">For example, the following code automatically enumerates over all permutational symmetries and orders the terms in canonical order:</span></span> 
```csharp
    // Load the namespace containing fermion objects. This
    // example also uses LINQ queries.
    using Microsoft.Quantum.Chemistry.Fermion;
    using System.Linq;

    // Create a `OrbitalIntegral` instance to store a two-electron molecular 
    // orbital integral data.
    var orbitalIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // Create an `OrbitalIntegralHamiltonian` instance to store the orbital integral
    // terms
    var orbitalIntegralHamiltonian = new OrbitalIntegralHamiltonian();
    orbitalIntegralHamiltonian.Add(orbitalIntegral);

    // Convert the orbital integral representation to a fermion
    // representation. This also requires choosing a convention for 
    // mapping spin orbital indices to integer indices.
    var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);

    // Alternatively, one can add orbital integrals directly to a fermion Hamiltonian
    // as follows. This automatically enumerates over all symmetries, and then
    // orders the `HermitianFermionTerm` instances in canonical order. We will need to
    // choose an indexing convention as well.
    fermionHamiltonian.AddRange(orbitalIntegral
        .ToHermitianFermionTerms(0, IndexConvention.UpDown)
        .Select(o => (o.Item1, o.Item2.ToDoubleCoeff())));
```
