---
title: Druhý kvantizační
description: Přečtěte si o druhém kvantizační přístupu k modelování elektronických struktur při programování.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6becd348f7b3957cb60b16bbd5a28228527e1d4c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835804"
---
# <a name="second-quantization"></a>Druhý kvantizační

Druhý kvantizační podívá na problém elektronické struktury v jiném objektivu.
Místo přiřazování každé z $N _e $ Electrons ke konkrétnímu stavu (nebo Orbital), druhé kvantizační sleduje každé Orbital a ukládá, zda je v každé z nich přítomna nějaká elektronická část a zároveň automaticky zajišťuje vlastnosti symetrie odpovídající funkce Wave.
To je důležité, protože umožňuje určit modely chemickéch procesorů, aniž byste se museli starat o symmetrizing stav vstupu (jak je vyžadováno pro fermions), a také proto, že druhý kvantizační umožňuje simulaci takových modelů pomocí malých počítačů.

Jako příklad druhé kvantizační v akci se předpokládá, že $ \ psi_0 \cdots \ psi_ {N-1} $ jsou orthonormal sadou prostorových orbitals.
Tyto orbitals se volí tak, aby reprezentovaly systém co nejpřesněji v uvažovaném rámci omezeného základního nastavení.
Běžným příkladem takových orbitals jsou atomické orbitalsy, které tvoří eigenbasis pro Atom vodík.
Vzhledem k tomu, že Electrons mají dva stavy otočení, dvě Electrons mohou být crammed do každého takového prostorového Orbital.
To znamená, že platné základní stavy jsou ve formátu $ \ psi_ {0, \uparrow}, \ldots, \ psi_ {N-1, \uparrow}, \ psi_ {0, \downarrow}, \ldots, \ psi_ {N-1, \downarrow} $ WHERE $ \uparrow $ a $ \downarrow $ jsou štítky, které určují dva eigenstates stupeň volnosti.
Tento kombinovaný index $ (j, \sigma) $ pro $ \sigma \in \{ \uparrow, \downarrow \} $ se označuje jako míchy, protože ukládá jak prostor, tak i stupeň volnosti.
V knihovně chemie jsou orbitalsy uloženy v `SpinOrbital` datové struktuře a jsou vytvořeny následujícím způsobem.

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

To znamená, že můžeme považovat základ pro otočení i prostorové části funkce Wave jako $ \ psi_ {0} \cdots \ psi_ {2N-1} $, kde každá z indexů teď představuje výčet $ (j, \sigma) $.
Jeden možný výčet je $g (j, \sigma) = j + N\sigma $.
Další možný výčet je $h (j, \sigma) = 2 * j + \sigma $.
Knihovna složení doby provozu může tyto konvence použít a na orbitals v takovém kódování lze vytvořit instanci následujícím způsobem.

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

V případě systémů fermionic se Pauli princip vyloučení zabrání tomu, aby se v jakémkoli Orbital ve stejnou dobu zobrazoval více než jeden elektron.
To znamená, že můžeme napsat dva právní stavy pro $ \ psi_1 $ jako \begin{Equation} \ psi_1 \rightarrow \begin{Cases} \ket {0} _1 & \Text{if $ \ psi_1 $ není obsazené.} \\\
\ket {1} _1 & \Text{if $ \ psi_1 $ je obsazeno.} \end{Cases} \end{Equation} toto kódování je skvělé pro počítače, protože to znamená, že je možné uložit elektronické povolání jako jeden bit.

Stavy povolání pro orbitals $2N $ se můžou podobně ukládat v $2N $ qubits.
Pokud například $N = $2, pak stav $ $ \ket {0} \ket {1} \ket {1} \ket {0} , $ $

by odpovídaly číselníku orbitals $1 $ a $2 $, který je obsazený zbývajícím prázdným.
Podobně platí, že stav $ $ \ket {0} \equiv \ket {0} _ {0} \cdots {0} \ket_{N-1}, $ $

nemá žádný Electrons a je známý jako "podtlak State".

Krásné vedlejší účinky druhé kvantizační je, že už nemusíme explicitně sledovat anti-symetrii stavu nedodržení.
To proto, že jak uvidíme, anti-symetrie státu se místo toho reprezentuje prostřednictvím pravidel ochrany před přístavování operátorů, kteří vytvářejí a zničí elektronické povolání míchy Orbital.

## <a name="fermionic-operators"></a>Fermionic operátory

Dva základní operátory, které fungují na quantized základních vektorů, se nazývají vytváření a Annihilation operátory.
Tyto operátory vkládají nebo zničí Electrons v konkrétním umístění.
Jsou označené $a ^ \ dagger_j $ a $a _j $.

Například \begin{Align} a ^ \ dagger_1 \ket {0} _1 = \ket {1} _1, \quad a ^ \ dagger_1 \ket {1} _1 = 0, \quad A_1 \ket {0} _1 = 0, \quad A_1 \ket {1} _1 = \ket {0} _1.
\end{align} Všimněte si, že tady $a ^ \ dagger_1 \ket {1} _1 = 0 $ a $a _1 \ket {0} _1 $ Dej nulový vektor not $ \ket {0} _1 $.
Takové operátory proto nejsou ani Hermitian ani nejednotná.
Pro obecné vytváření a Annihilation operátory Představujeme pomocí <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> typu.
Například jeden operátor vytvoření je reprezentován následujícím způsobem.

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

Pomocí takových operátorů můžeme také vyjádřit odpověď $ $ \ket {0} \ket {1} \ket {1} \ket {0} = a ^ \ dagger_1 ^ \ dagger_2 \ket {0} ^ {\otimes 4}.
$ $ Tato sekvence operátorů by se vytvořila v rámci knihovny simulace Hamiltonian pomocí kódu jazyka C#, který je podobný případu s jedním otočením Orbital, který se považuje za výše uvedený výše:
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

V případě systému $k $ Fermions ve druhém kvantizační akce operátoru vytvoření $a ^ \ dagger_i $ je dána $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $ $ a $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k} = 0, kde $S _i = \ sum_ {j<i} ^ \ dagger_j a_j $ Measures celkový počet Fermions, které jsou ve stavu jedné částice a které mají index $j < i $.

Třetí operátor se také často používá ve druhém quantized reprezentace.
Tento operátor je označován jako operátor Number a je definován pomocí \begin{Equation} n_i = a ^ \ dagger_i a_i.
\end{Equation} Tento operátor počítá povolání daného číselníku Orbital, což znamená \begin{align} n_i \ket {0} _i &= 0 \ číslo\\\
n_i \ket {1} _i &= \ket {1} _i.
\end{align} podobně jako v předchozích `FermionTerm` příkladech je tento operátor číslo konstruován následujícím způsobem.
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have omitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

Subtlety se při použití operátorů vytváření nebo Annihilation v systémech fermionic objeví.
Vyžadujeme, aby jakýkoliv platný stav v nenáročném stavu byl v rámci výměny popisků příliš symetrický.
To znamená, že $ $ a ^ \ dagger_2 a ^ \ dagger_1 \ket {0} =-a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} .
$ $ Tyto operátory jsou označovány jako "" anti-dojíždění "a obecně pro všechny $i, j $ máme \begin{Align} a ^ \ dagger_i a ^ \ dagger_j =-(1-\ delta_ {i, j}) ^ \ dagger_j a ^ \ dagger_i, \quad a ^ \ dagger_i a_j = \ delta_ {i, j}-a_j ^ \ dagger_i.
\end{align} <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> se proto považují za neekvivalentní následující dvě instance.
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

Požadavek na to, aby každá z operátorů vytváření byla dojíždění, znamená, že použití druhé reprezentace quantized předkládá výzvy, na které čelí anti-symetrie Fermions.
Místo toho se výzva v naší definici operátorů vytváření objeví znovu. 

Pomocí pravidel pro účely nedostatku do zaměstnání některé `LadderSequence` instance ve skutečnosti odpovídají stejné sekvenci fermionic operátorů, někdy až po znaménku mínus.
Zvažte například Hamiltonian $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 $.
To vám umožní definovat kanonické řazení pro každé z nich `FermionTerm` .
Všechny `FermionTerm` jsou automaticky vloženy do kanonického pořadí následujícím způsobem.
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

## <a name="second-quantized-fermionic-hamiltonian"></a>Druhý – quantized Fermionic Hamiltonian

Je možné, že Hamiltonian v modelech neunsurprisingch hodnot [pro elektronické systémy](xref:microsoft.quantum.chemistry.concepts.quantummodels) se dají zapisovat z podmínek vytváření a annihilationch operátorů.
Konkrétně platí, že pokud $ \psi \_ j $ jsou orbitals, které tvoří základ, pak

\begin{Equation} \hat{H} = \sum \_ {pq} H \_ {pq} a ^ \dagger \_ p a \_ q + \frac {1} {2} \sum \_ {pqrs} h \_ {pqrs} a ^ \dagger \_ p a ^ \dagger \_ q a \_ RA \_ s + H \_ {\textrm NUC}, \label{EQ: totalHam} \end{Equation}, kde $h \_ {\textrm NUC} $ je jaderná energie (což je konstanta ve sbližování po Oppenheimer) a

\begin{align} h \_ {pq} &= \int \_ {-\infty} ^ \infty \psi ^ \* \_ p (x \_ 1) \left (-\Frac{\nabla ^ 2} {2} + V (x \_ 1) \right) \psi \_ q (x \_ 1) \mathrm{d} ^ 3x \_ 1, \end{align}

kde $V (x) $ je potenciál v poli střední hodnoty a

\begin{align} h \_ {pqrs} &= \int \_ {-\infty} ^ \infty \int \_ {-\infty} ^ \infty\psi \_ p ^ \* (x \_ 1) \psi \_ q ^ \* (x \_ 2) \left (\frac {1} {| x_1-x_2 |} \right) \psi \_ r (x \_ 2) \psi \_ s (x \_ 1) \mathrm{d} ^ 3x \_ 1 \ mathrm {d} ^ 3x \_ 2. \ Label {EQ: integrály} \end{align}

Výrazy $h \_ {pq} $ jsou označovány jako integrální integrály, protože všechny takové výrazy zahrnují pouze jeden Electrons a podobně $h \_ {pqrs} $ jsou dva elektronické integrály.
Jsou označovány jako integrály, protože výpočet hodnot těchto koeficientů vyžaduje integrál.
Jedna elektronická podmínka popisuje kinetiku vlastní energie jednotlivých Electrons a jejich interakce s elektrickými poli Nuclei.
Dva elektronické integrály na druhé straně popisují interakce mezi Electrons.

Intuition, co znamenají tyto výrazy, se dají mohli z operátorů vytváření a Annihilation, které tvoří každou z nich.
Například $h _ {pq} a ^ \ dagger_p a_q $ popisuje skákající od Orbital $q $, aby se Orbital $p $.
Podobně výraz $h _ {pqrs} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (pro jedinečné $p, q, r, s $), popisuje dva electronsy ve orbitals $r $ a $s $ bodový od sebe a končí orbitals $p $ a $q $.
Pokud $r = q $ a $p = s $, pak $h _ {prrp} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ poskytuje energetickou pokutu spojenou s oběma electronsy blízko sebe, ale nepopisuje dynamický proces.

Takový Hamiltonians můžeme zastupovat pomocí `FermionHamiltonian` třídy, která je v podstatě seznam obsahující všechny požadované `FermionTerm` instance.
Protože Hamiltonians jsou Hermitian podle definice, indexuje výrazy pomocí specializovaného typu `HermitianFermionTerm` , který také používá Hermitian symetrie při kontrole, zda jsou výrazy ekvivalentní.

Můžeme vytvořit několik příkladů.
Vezměte v úvahu Hamiltonian $ \hat{H} = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $.
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
Tuto konstrukci můžeme zjednodušit pomocí faktu, že operátory Hamiltonian jsou Hermitian operátory.
Při přidávání podmínek do Hamiltonian pomocí `Add` se předpokládá, že jakýkoli neHermitian termín, jako je, se `fermionTerm0` spáruje s jeho Hermitianem.
Proto následující fragment kódu představuje také stejný Hamiltonian:
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

Pomocí pravidel pro účely boje proti dojíždění některé `FermionTerm` instance ve Hamiltonian ve skutečnosti odpovídají stejné sekvenci fermionic Operators, někdy až k znaménku minus.
Zvažte například Hamiltonian $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $, což je součet podmínek vytvořených výše.
Nemusí být vždy jasné pro uživatele, že se jedná o ekvivalentní výrazy, a proto je lze do Hamiltonian přidat samostatně.
Případně může být jedna z nich zajímat úpravu již existujících podmínek v Hamiltonian.
V těchto případech můžeme kombinovat ekvivalentní výrazy následujícím způsobem.
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
Kombinací koeficientů ekvivalentních podmínek snižujeme celkový počet podmínek v Hamiltonian.
Později se tím sníží počet bran, které jsou potřeba k simulaci Hamiltonian.

### <a name="internal-representation"></a>Interní reprezentace

Fermionic Hamiltonian s interakcemi jednoho a dvou částí je zastoupená v druhé-quantized zápisu jako

$ $ \begin{align} H = \sum \_ {pq} h \_ {pq} a ^ \dagger \_ {p} a \_ {q} + \frac {1} {2} \sum \_ {pqrs} H \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s}.
\end{align} $ $

V tomto zápisu má maximálně $N ^ 2 + N ^ 4 $ hodnot.
Mnohé z těchto koeficientů však mohou být shromažďovány, protože odpovídají stejnému operátoru.
Například v případě, kdy $p, q, r, s $ jsou odlišné indexy, můžeme použít pravidla pro ochranu před rozužíváním, aby se zobrazila tato: $ $ a ^ \dagger \_ {p} a ^ \dagger \_ {q} \_ {r} a \_ {s} =-a ^ \dagger \_ {q} a ^ \dagger \_ {p} a { \_ r} a \_ {s} =-a ^ \dagger \_ {p} a ^ \dagger {q} a { \_ \_ \_ r} = a ^ \dagger \_ {q} a ^ \dagger \_ {p} \_ \_ a {r}.
$$

Kromě toho, když je $H $ Hermitian, každý neHermitian fermionic operátor, řekněme $h \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} $, má přidaný Hermitian, který se nachází také v $H $. Aby bylo možné jedinečně indexovat skupiny podmínek, které jsou charakterizovány těmito symmetries, definujeme kanonické řazení pro indexy $ (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) v jakékoli posloupnosti operátorů $n + m $ fermionic $a ^ \dagger \_ {i \_ 1} \cdots a ^ \dagger \_ {i \_ n} a \_ {j \_ 1} \cdots a \_ {j \_ m} $as následující:
-   Všechny operátory vytváření $a ^ \dagger \_ {i \_ \cdot} $ jsou umístěné před všemi operátory Annihilation $a \_ {j \_ \cdot} $.
-   Všechny indexy operátorů vytvoření jsou seřazené ve vzestupném pořadí, což je $i \_ 1< i \_ 2< \cdots < i \_ n $.
-   Všechny indexy operátorů Annihilation jsou seřazené v sestupném pořadí, což je $j \_ 1> j \_ 2 \cdots > j \_ m $.
-   Index nejvíce vlevo je menší nebo roven indexu, který je nejvíce vpravo, který je $i \_ 1 \ Le j \_ m $.

Sdělte nám tuto sadu s kanonickými řazenými indexy jako $ $ \begin{align} (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) \in S \_ {n, m}.
\end{align} $ $

V tomto kanonickém řazení se fermionic Hamiltonian může vyjádřit jako $ $ \begin{align} H = \sum \_ {(p, q) \In S \_ {1,1} } H \_ {pq} \frac{a ^ \dagger \_ {p} a \_ {q} + a ^ \dagger \_ {q} a \_ {p}} {2} + \sum \_ {(p, q, r, s) \in S \_ {2,2} } H ' \_ {pqrs} \frac{a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} + a ^ \dagger \_ {S} a ^ \dagger \_ {r} \_ {q} a \_ {p}} {2} , \end{align} $ $ s vhodně přizpůsobeným jedním a dvěma elektronem integrály $h \_ {pq} $ a $h \_ {pqrs} $, v uvedeném pořadí.

