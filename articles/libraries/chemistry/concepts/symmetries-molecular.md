---
title: Symmetries molekulových integrálů | Microsoft Docs
description: Symmetries molekulových integrálů koncepčních dokumentů
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: 041d600bc8d65e7d67f5fe7d61a69426fb42ffbc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442392"
---
# <a name="symmetries-of-molecular-integrals"></a>Symmetries molekulových integrálů

Základní symetrie Coulomb Hamiltonian, což je Hamiltonian v [modelech pro práci s elektronickými systémy](xref:microsoft.quantum.chemistry.concepts.quantummodels), které popisují Electrons interakci elektricky navzájem a s Nuclei, vede k řadě symmetries, které mohou být zneužito ke komprimaci podmínek v Hamiltonian.
Obecně platí, že pokud se pro základní funkce $ \psi_j $ neprovádí žádné další předpoklady, máme jenom tento \begin{Equation} H_ {pqrs} = H_ {QPSR}, \tag{★} \label{EQ: hpqrs} \end{Equation}, který se dá hned zobrazit z integrálních hodnot v [modelech v případě Elektronické systémy](xref:microsoft.quantum.chemistry.concepts.quantummodels) po zaznamenání, že jejich hodnoty zůstávají stejné, pokud $p, q $ a $r, s $ se zamění z ochrany proti dojíždění.

Pokud předpokládáme, že orbitals jsou reálné (stejně jako u Gaussovskéch orbitalch bází), pak dál máme \begin{Equation} H_ {pqrs} = H_ {QPSR} = H_ {srqp} = H_ {rspq} = H_ {rqps} = H_ {psrq} = H_ {SPQR} = H_ {qrsp} .\tag {★} \label{EQ: hpqrsreal} \end{ rovnice} vzhledem k tomu, že tyto předpoklady jsou uloženy, můžeme použít výše uvedené symmetries k omezení dat potřebných k uložení prvků matrice Hamiltonian o faktoru $8 $; i když tomu tak je, umožňuje importovat data konzistentním způsobem, který je trochu náročnější.
Knihovna simulace Hamiltonian má podrutiny, které lze použít k importu integrálních souborů buď z [LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) , nebo přímo z [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).

Molekulové Orbital integrály (tj. $h\_{pq} $ a $h\_{pqrs} $), jako jsou reprezentovány pomocí typu `OrbitalIntegral`, který poskytuje řadu užitečných funkcí pro vyjádření této symetrie.
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

Kromě výčtu všech Orbital integrálů, které jsou číselně identické, se může vygenerovat seznam všech Orbital indexů obsažených v Hamiltonian reprezentovaných `OrbitalIntegral`.
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

Namísto sestavování Fermionicho Hamiltonian přidáním `FermionTerm`s můžete automaticky přidat všechny příslušné výrazy, které odpovídají jednotlivým Orbital integrálu.
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
