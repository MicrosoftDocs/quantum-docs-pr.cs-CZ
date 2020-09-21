---
title: Symmetries molekulových integrálů
description: Přečtěte si o použití Q# typu OrbitalIntegral k zobrazení výčtu molekulových symmetries.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9ebb8e9bda06967d3cfa002a7d074933d9135ada
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833821"
---
# <a name="symmetries-of-molecular-integrals"></a>Symmetries molekulových integrálů

Podstata symetrie Coulomb Hamiltonian, která je Hamiltonian v [modelech pro práci s elektronickými systémy](xref:microsoft.quantum.chemistry.concepts.quantummodels), která popisuje Electrons interakci elektricky navzájem a s Nuclei, vede k tomu, že je možné využít řadu symmetries, které lze zneužít ke komprimaci podmínek v Hamiltonian.
Obecně platí, že pokud se neprovádí žádné další předpoklady pro základní funkce $ \ psi_j $, máme jenom tento \begin{Equation} h_ {pqrs} = h_ {QPSR}. \tag{★} \label{EQ: hpqrs} \end{Equation}, který se dá hned zobrazit z integrálních prvků v [modelech nečinnosti u elektronických systémů](xref:microsoft.quantum.chemistry.concepts.quantummodels) , když se Poklade, že jejich hodnoty zůstávají stejné, pokud se $p, q $ a $r, s $ mění z ochrany po rozjíždění.

Pokud předpokládáme, že orbitals jsou reálné (stejně jako pro Gaussovské orbitalé základny), budeme dál mít k dispozici \begin{Equation} h_ {pqrs} = h_ {QPSR} = h_ {srqp} = h_ {rspq} = h_ {rqps} = H_ {psrq} = h_ {SPQR} = h_ {qrsp} .\tag {★} \label{EQ: hpqrsreal} \end{Equation}, které tyto předpoklady obsahují, můžeme použít výše uvedené symmetries k omezení dat potřebných k uložení prvků matrice Hamiltonian o faktoru $8 $; i když tomu tak je, umožňuje importovat data konzistentním způsobem, který je trochu náročnější.
Knihovna simulace Hamiltonian má podrutiny, které lze použít k importu integrálních souborů buď z [LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) , nebo přímo z [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).

Molekulové Orbital integrály (tj. $h \_ {pq} $ a $h \_ {pqrs} $), jako jsou reprezentovány pomocí `OrbitalIntegral` typu, který poskytuje řadu užitečných funkcí pro vyjádření této symetrie.
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

Kromě výčtu všech Orbital integrálů, které jsou číselně identické, je možné vygenerovat seznam všech Orbital indexů obsažených v Hamiltonian reprezentovaných pomocí `OrbitalIntegral` .
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a>Sestavování Fermionic Hamiltonians z molekulových integrálů

Namísto sestavování Fermionic Hamiltonian přidáním `FermionTerm` s můžete automaticky přidat všechny příslušné výrazy, které odpovídají jednotlivým Orbital integrálu.
Například následující kód automaticky vytvoří výčet pro všechny permutace symmetries a vyřadí výrazy v kanonickém pořadí: 
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
