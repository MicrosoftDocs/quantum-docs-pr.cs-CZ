---
title: Načtení hamiltoniánu ze souboru
description: Naučte se, jak automaticky generovat velké Hamiltonian pomocí schématu Broombridge.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.loadhamiltonian
no-loc:
- Q#
- $$v
ms.openlocfilehash: 57e25bf55009797b01695cef0f3d29b94662ccc0
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869234"
---
# <a name="loading-a-hamiltonian-from-file"></a>Načtení hamiltoniánu ze souboru
Dříve jsme vytvořili Hamiltonians přidáním jednotlivých podmínek. I když je to v malých příkladech jemné, je chemie ve velkém měřítku vyžadovat Hamiltonians s miliony nebo miliardami podmínek. Takové Hamiltonians generované balíčky chemie, jako je NWChem, je příliš velké pro import rukou. V této ukázce ilustruje, jak `FermionHamiltonian` může být instance automaticky generovaná z molekuly reprezentovaných [Broombridge schématem](xref:microsoft.quantum.libraries.chemistry.schema.broombridge). V případě referenčních informací může být jedna z nich podrobena `LithiumHydrideGUI` `RunSimulation` ukázce. K dispozici je také omezená podpora pro import z formátu spotřebovaného [LIQUi |>](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/).

Vezměte v úvahu příklad molekuly dusíku, který je k dispozici ve `IntegralData/YAML` složce úložiště ukázek. Metoda pro načtení `Broombridge` schématu je jednoduchá.

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

Schéma Broombridge obsahuje také návrhy na přípravu počátečního stavu. Popisky, např. `"|G⟩"` nebo `"|E1⟩"` , mohou být pro tyto stavy patrné kontrolou souboru. Aby bylo možné připravit tyto počáteční stavy, využívané algoritmy pro stavové služby `qSharpData` Q# se získají podobně jako v [předchozí části](xref:microsoft.quantum.chemistry.examples.energyestimate), ale s dalším parametrem, který vybírá požadovaný počáteční stav. Příklad:
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

Hamiltonian můžeme také načíst z LIQUi |> formátu pomocí velmi podobné syntaxe. 

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
