---
title: Hartree – Fock teorie
description: Seznamte se s Hartree – Fock teoreticky, což je jednoduchý způsob, jak vytvořit počáteční stav pro systémy na více systémů.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: 6fa63cbe13fe98565ffb42b56f3ade86720cedb3
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274662"
---
# <a name="hartreefock-theory"></a>Hartree – teorie Fock

Nejdůležitějším množstvím v simulaci nestavových funkcí je například základní stav, což je minimální energetická eigenvector matice Hamiltonian.
Důvodem je to, že pro většinu molekul za pokojové teploty, jako jsou míry reakce, se zachází z bezplatných rozdílů energie mezi stavy, které popisují začátek a konec kroku v reakci na reakci a při pokojové teplotě, jako je například uzemněný stav.
I když je stav vozovky obvykle moc velký, nemusíte se učit (dokonce i u počítače s velkým množstvím), protože se jedná o distribuci s exponenciálně velkým počtem konfigurací.
Množství, jako je pozemní energie, se může naučit.
Pokud má například $ \ket{\psi} $ jakýkoliv čistý stav, pak \begin{Equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{Equation} poskytuje střední energii, kterou má systém v tomto stavu.
Stav země je pak stav, který poskytuje nejmenší takovou hodnotu. Výsledkem je, že volba stavu, který je co nejblíže skutečnému stavu, je velmi důležitý pro odhad energie buď přímo (jak se provádí v variaci eigensolvers), nebo prostřednictvím odhadu fáze.

Hartree – teoretická Fock představuje jednoduchý způsob, jak vytvořit počáteční stav pro systémy s více poli. Výsledkem je jedna Slatera determinanta pro základní stav systému. Za tímto účelem vyhledá rotaci v rámci Fock místa, které minimalizuje stav energie na zemi. Konkrétně pro systém $N $ Electrons metoda provádí rotační \begin{Equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket {0} \mapsto \ prod_ {j = 0} ^ {n-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket {0} \defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket {0} , \end{Equation} pomocí anti-Hermitian (tj. $u =-u ^ \dagger $) Matrix $u = \ sum_ {pq} u_ {pq} a ^ \ dagger_p a_q $. Je potřeba poznamenat, že matice $u $ představuje rotace Orbital a $ \widetilde{a} ^ \ dagger_j $ a $ \widetilde{a} _j $ představují operátory vytváření a Annihilation pro Electrons, které zaujímají Hartree – Fock molekulární číselník orbitals.


Matice $u $ je pak optimalizovaná tak, aby se minimalizovala očekávaná hodnota Energy $ \bra {0} \ prod_ {j = 0} ^ {n-1} \widetilde{a} \_ j H \prod \_ {k = 0} ^ {N-1} \widetilde{a} ^ \ dagger_k \ket {0} $. I když takové problémy s optimalizací můžou být pevně tvrdé, v praxi se Hartree algoritmus Fock, takže se v praxi rychle konverguje k problému s optimalizací téměř optimálního řešení, zejména pro molekuly v prostředí rovnováhy. Tyto stavy můžeme specifikovat jako instanci `FermionWavefunction` objektu. Například stav $a ^ \ dagger_ {1} a ^ \ dagger_ {2} a ^ \ dagger_ {6} \ket {0} $ je vytvořena v knihovně chemie následujícím způsobem.
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
Je také možné indexovat funkce Wave s `SpinOrbital` indexy a pak tyto indexy převést na celá čísla následujícím způsobem.
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

Nejefektivnější funkce o Hartree – Fock je to, že poskytuje stav bez stavu, který nemá žádný entanglement mezi Electrons.
To znamená, že často poskytuje vhodný kvalitativní popis vlastností molekulových systémů. 

Stav Hartree-Fock může být také znovu vytvořen z `FermionHamiltonian` následujícího příkladu.
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

Získání přesných výsledků, zejména pro silně korelační systémy, ale vyžaduje stavy, které překračují rámec Hartree – Fock teorie.
