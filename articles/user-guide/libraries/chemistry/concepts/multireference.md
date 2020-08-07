---
title: Korelované vlnové funkce
description: Seznamte se s dynamickými a nedynamickými korelacemi v wavefunctions pomocí knihovny Microsoft pro složení nedodržení.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0066d676205901d4f2d41538684f9ba57407eb82
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869558"
---
# <a name="correlated-wavefunctions"></a>Korelované vlnové funkce

Pro mnoho systémů, zejména v blízkosti geometrie rovnováhy, [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) teoreticky poskytuje kvalitativní popis vlastností molekul prostřednictvím referenčního stavu s jedním determinantem. Aby však bylo možné dosáhnout kvantitativní přesnosti, musí být jedna z nich také zvážena z relačních účinků. 

V tomto kontextu je důležité dinstinguish mezi dynamickými i nedynamickými korelacemi.
Dynamické korelace vznikají od neelectronsch, které by měly zůstat v souvislosti s mezielektronickým přepohonem. Tento efekt můžete modelovat tím, že zvažujete excitations z referenčního stavu Electrons. Nedynamická korelace nastanou, když je wavefunction na základě dvou nebo více konfigurací v pořadí zeroth, a to i v případě, že dosáhnete pouze kvalitativního popisu systému.
To vyžaduje nadpolohu rozhodujících determinantů a je příkladem více wavefunctionch odkazů.

Knihovna složení poskytuje způsob, jak zadat zeroth objednávky wavefunction pro problém s více odkazy jako nadmnožinu rozhodujících míst. Tento přístup, který volá zhuštěné wavefunctionsy, je platný, pokud pouze některé součásti postačují k určení nadpozice. Knihovna také poskytuje metodu pro zahrnutí dynamických korelací na základě jednoho determinantu pomocí generalizované jednotně Ansatz clusteru. Kromě toho také sestaví okruhy na základě stavu, které generují tyto stavy na počítači s více stroji. Tyto stavy mohou být zadány ve [schématu Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)a my také poskytujeme funkci pro ruční určení těchto stavů prostřednictvím knihovny složení.

## <a name="sparse-multi-reference-wavefunction"></a>Wavefunction zhuštěných více odkazů
Stav vícenásobných odkazů $ \ket{\ psi_ {\rm {MCSCF}}} $ se dá explicitně zadat jako lineární kombinace $N $-elektron Slater determininants.
\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1, i_2, \cdots, i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots a ^ \ dagger_ {i_N} \ket {0} .
\end{align} například stav $ \propto (0,1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0,2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) \ket {0} $ může být uveden v knihovně chemie následujícím způsobem.
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
Tato explicitní reprezentace komponent nadpozice je platná, pokud je třeba zadat pouze některé součásti. Při použití této reprezentace by se neměla používat tato reprezentace, pokud je potřeba k přesnému zachycení požadovaného stavu použít spoustu součástí. Důvodem je, že se jedná o cenu za využití okruhu, která tento stav připraví na počítač s více procesory, který se škáluje alespoň lineárně s počtem komponent na více pozicích a s největší kvadratickou s jednou normou amplitudy pozice.

## <a name="unitary-coupled-cluster-wavefunction"></a>Jednotně kombinovaná wavefunction clusteru
Pomocí knihovny chemistery je taky možné zadat jednotnou kombinaci wavefunction $ \ket{\ psi_ {\rm {UCC}}} $. V této situaci máme jediný determinant referenčního stavu, například $ \ket{\ psi_ {\rm{SCF}}} $. Komponenty pro jednotně wavefunction clustery se pak implicitně určí prostřednictvím jednotkového operátoru, který funguje v referenčním stavu.
Tento operátor s jednou jednotkou se běžně zapisuje jako $e ^ {T-T ^ \dagger} $, kde $T-T ^ \dagger $ je operátor Hermitianho clusteru. Proto \begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}.
\end{align}

Také je běžné rozdělit operátor clusteru $T = T_1 + T_2 + \cdots $ do částí, kde každá část $T _j $ obsahuje označení $j $-tělo. V generalizované kombinaci mezi clustery (jednoduchou) má operátor clusteru s jedním tělem () ve formě \begin{align} T_1 = \ sum_ {pq} T ^ {p} _ {q} a ^ \ dagger_p a_q, \end{align}

a \begin{align} operátor clusteru (Double) má tvar T_2 = \ sum_ {pqrs} T ^ {pq} _ {RS} a ^ \ dagger_p ^ \ dagger_q a_r a_s.
\end{align}

Je možné, že se jedná o výrazy s vyšším pořadím (Trojnásobky, čtyřikrát atd.), ale ne aktuálně podporované knihovnou chemie.

Například nechejte $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} $ a nechte $T = 0,123 a ^ \ dagger_0 A_1 + 0,456 a ^ \ dagger_0a ^ \ dagger_3 a_1 A_2-0,789 a ^ \ dagger_3a ^ \ dagger_2 A_1 A_0 $. Pak je tento stav vytvořen v knihovně chemie následujícím způsobem.
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

Je možné provést explicitní convervation místo toho, aby namísto `SpinOrbital` celočíselných indexů určila indexy. Můžete například let $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1, \uparrow} a ^ \ dagger_ {2, \downarrow}\ket {0} $ a let $T = 0,123 a ^ \ dagger_ {0, \uparrow} a_ {1, \uparrow} + 0,456 a ^ \ dagger_ {0, \uparrow} a ^ \ dagger_ {3, \downarrow} a_ {1, \uparrow} a_ {2, \downarrow}-0,789 a ^ \ dagger_ {3, \uparrow} a ^ \ dagger_ {2, \uparrow} a_ {1, \uparrow} a_ {0, \uparrow} $ by měl být číselník convserving. Pak je tento stav vytvořen v knihovně chemie následujícím způsobem.
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

Nabízíme také pohodlí, která vytvoří výčet pro všechny operátory clusterů konverzující, které annihilate jenom, orbitals a nadchnou jenom na neobsazený číselník.
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
