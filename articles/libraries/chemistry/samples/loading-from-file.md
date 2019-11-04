---
title: Načítá se Hamiltonian ze souboru | Microsoft Docs
description: Načtení Hamiltonian ze souboru docs
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.loadhamiltonian
ms.openlocfilehash: 9902e95b09d38323b4b91c29ab897a4f0124b6cd
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184181"
---
## <a name="loading-a-hamiltonian-from-file"></a>Načítá se soubor Hamiltonian ze souboru.
Dříve jsme vytvořili Hamiltonians přidáním jednotlivých podmínek. I když je to v malých příkladech jemné, je chemie ve velkém měřítku vyžadovat Hamiltonians s miliony nebo miliardami podmínek. Takové Hamiltonians generované balíčky chemie, jako je NWChem, je příliš velké pro import rukou. V této ukázce ukážeme, jak může být instance `FermionHamiltonian` automaticky vygenerována z molekuly reprezentovaných [schématem Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge). V případě referenčních informací může být jedna ukázka `LithiumHydrideGUI` nebo ukázka `RunSimulation`. K dispozici je také omezená podpora pro import z formátu spotřebovaného [LIQUi | >](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/).

Vezměte v úvahu příklad molekuly dusíku, který je k dispozici ve složce `IntegralData/YAML` v úložišti ukázek. Metoda pro načtení `Broombridge`ho schématu je jednoduchá.

```csharp
// This is the name of the file we want to load
var filename = @"n2_1_00Re_sto3g.nw.out.yaml";
// This is the directory containing the file
var root = @"IntegralData\YAML";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge($@"{root}\{filename}");

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.First()`, which selects the first element of the list.
var problem = broombridge.ProblemDescriptions.First();

// This extracts the `OrbitalIntegralHamiltonian` from Broombridge format,
// then converts it to a fermion Hamiltonian, then to a Jordan-Wigner
// representation.
var orbitalIntegralHamiltonian = problem.OrbitalIntegralHamiltonian;
var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);
var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);
```

Schéma Broombridge obsahuje také návrhy na přípravu počátečního stavu. Popisky, např. `"|G⟩"` nebo `"|E1⟩"`, lze pro tyto stavy zobrazit zkontrolováním souboru. Pro přípravu těchto počátečních stavů se `qSharpData` spotřebující algoritmy Q # získává podobně jako v [předchozí části](xref:microsoft.quantum.chemistry.examples.energyestimate), ale s dalším parametrem, který vybírá požadovaný počáteční stav. Například
```csharp
// The desired initial state, assuming that a description of it is present in the
// Broombridge schema.
var state = "|E1>";
var wavefunction = problem.Wavefunctions[state].ToIndexing(IndexConvention.UpDown);

// This creates the qSharpData consumable by the Q# chemistry library algorithms.
var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
var qSharpWavefunctionData = wavefunction.ToQSharpFormat();
var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

Všechny výše uvedené kroky mohou být zkráceny pomocí poskytovaných praktických metod, a to následujícím způsobem.
```csharp
// This is the name of the file we want to load
var filename = "...";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge(filename);

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.Single()`, which selects the only element of the list.
var problem = broombridge.ProblemDescriptions.Single();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
// If no state is specified, the Hartree-Fock state is used by default.
var qSharpData = problem.ToQSharpFormat("|E1>");
```

Hamiltonian můžeme také načíst z formátu LIQUi | > pomocí velmi podobné syntaxe. 

```csharp
// This is the name of the file we want to load
var filename = @"fe2s2_sto3g.dat"; // This is Ferrodoxin.
// This is the directory containing the file
var root = @"IntegralData\Liquid";

// Deserialize the LiQuiD format.
var problem = LiQuiD.Deserialize($@"{root}\{filename}").First();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
var qSharpData = problem.ToQSharpFormat();
```

Pomocí tohoto postupu z jakékoli instance Broombridge nebo jakéhokoli přechodného kroku se můžou v zadaném problému s elektronickými strukturami spustit algoritmy, jako je například odhad fáze.