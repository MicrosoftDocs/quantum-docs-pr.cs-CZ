---
title: Simulace Hamiltonian Dynamics
description: Naučte se používat vzorce Trotter-Suzuki a qubitization pro práci s simulacemi Hamiltonian.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
no-loc:
- Q#
- $$v
ms.openlocfilehash: a303d54476e42b98a14c6b452227b0e1346567c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691888"
---
# <a name="simulating-hamiltonian-dynamics"></a>Simulace Hamiltonian Dynamics

Jakmile se Hamiltonian vyjádří jako součet základních operátorů, může se dynamika kompilovat do základních operací brány pomocí hostitele známých technik.
Mezi tři efektivní přístupy patří Trotter – vzorce Suzuki, lineární kombinace unitaries a qubitization.
Níže uvádíme tyto tři způsoby a poskytujeme konkrétní Q# Příklady implementace těchto metod pomocí knihovny simulace Hamiltonian.


## <a name="trottersuzuki-formulas"></a>Trotter – vzorce Suzuki
Vzorec na pozadí Trotter – vzorce Suzuki jsou jednoduché: vyjádřete Hamiltonian jako součet jednoduchého simulace Hamiltonians a pak přibližný celkový vývoj jako sekvence těchto jednodušších vývojů.
Konkrétně dejte $H = \ sum_ {j = 1} ^ m H_j $ být Hamiltonian.
Pak $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $ to znamená, že pokud $t \ll $1, bude chyba v této aproximaci zanedbatelná.
Všimněte si, že pokud $e ^ {-i H} $ byly normální exponenciální, chyba v této aproximaci nebude $O (m ^ 2 t ^ 2) $: by to bylo nula.
K této chybě dochází, protože $e ^ {-iHt} $ je exponenciální exponenciální a v důsledku toho dojde k chybě při použití tohoto vzorce z důvodu faktu, že $H _J $ podmínka neprobíhá po dojíždění ( *tj.* $H _J H_k \Ne H_k H_j $ všeobecně).

Pokud je $t $ velké, Trotter vzorce Suzuki se dají použít k tomu, aby se tento dynamika přesně simulovaly tím, že se rozbalí do sekvence krátkého časového intervalu.
Nechte $r $ počet kroků provedených v čase vývoje, takže pokaždé, když se krok spustí pro čas $t/r $. Potom máme $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ Right) ^ r + O (m ^ 2 t ^ 2/r), $ $ to znamená, že pokud se $r $ škáluje jako $m ^ 2 t ^ 2/\ Epsilon $, může být chyba vytvořená maximálně $ \epsilon $ pro všechny $ \epsilon>$0.

Přesnější sblížení lze sestavit pomocí sekvence exponenciálních exponenciálních operátorů, aby se chybové výrazy zrušily.
Nejjednodušší vzorec, druhý pořadí Trotter-Suzuki vzorec, má formu $ $ U_2 (t) = \left (\ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2R} \ prod_ {j = m} ^ 1 e ^ {-iH_j t/2R} \ Right) ^ r = e ^ {-iHt} + O (m ^ 3 t ^ 3/r ^ 2), $ $ chyba, kterou je možné udělat méně než $ \epsilon $ pro jakékoli $ \epsilon>$0, a to tak, že vyberete $r $ pro škálování jako $m ^ {3/2} t ^ {3/2}/\sqrt {\ Epsilon} $.

Vzorce s vyšším pořadím, konkrétně ($ 2k $ $0>$k), je možné sestavit rekurzivně: $ $ U_ {2k} (t) = [U_ {2k-2} (s_k \~ t)] ^ 2 U_ {2k-2} ([1-4s_k] t) [U_ {2k-2} (s_k \~ t)] ^ 2 = e ^ {-iHt} + O ((m t) ^ {2k + 1}/r ^ {2k}), $ $ where $s _k = (4-4 ^ {1/(2k-1)}) ^ {-1} $.

Nejjednodušší je následující vzorec čtvrtého řádu ($k = $2), který původně představila Suzuki: $ $ U_4 (t) = [U_2 (s_2 \~ t)] ^ 2 U_2 ([1-4s_2] t) [U_2 (S_2 \~ t)] ^ 2 = e ^ {-iHt} + O (m ^ 5t ^ 5/r ^ 4), $ $ WHERE $s _2 = (4-4 ^ {1/3}) ^ {-1} $.
Obecně platí, že je možné podobně vytvořit libovolně vyšší pořadí vzorců; Nicméně náklady vyplývající z použití složitějších integrátorů často převažují nad rámec čtvrtého řádu pro většinu praktických problémů.

Aby výše uvedené strategie fungovaly, potřebujeme metodu pro simulaci třídy typu "$e ^ {-iH_j t} $".
Nejjednodušší rodina Hamiltonians a pravděpodobně je nejužitečnější, kterou bychom mohli použít tady jsou Pauli operátory.
Operátory Pauli je možné snadno simulovat, protože je možné je diagonální pomocí operací Clifford (což jsou standardní brány ve výpočetním prostředí).
Po jejich objasnění můžete jejich eigenvalues najít vynásobením parity qubits, na které jednají.

Například $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ WHERE $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-IT} & 0 & 0 & 0 \\\
        0 & e ^ {i t} & 0 & 0 \\\
        0 & 0 & e ^ {IT} & 0 \\\
        0 & 0 & 0 & e ^ {-IT} \end{bmatrix}.
$ $ Sem $e ^ {-iHt} \ket {00} = e ^ {IT} \ket {00} $ a $e ^ {-iHt} \ket {01} = e ^ {-The} \ket {01} $, který se dá vidět přímo jako důsledek faktu, že parita $0 $ je $0 $, zatímco parita bitového řetězce $1 $ je $1 $.

Exponenciální operátory operátorů Pauli lze implementovat přímo Q# pomocí <xref:Microsoft.Quantum.Intrinsic.Exp> operace:
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

Pro Fermionic Hamiltonians, [Wigner (Jordánsko – rekompozici](xref:microsoft.quantum.chemistry.concepts.jordanwigner) ), vhodně namapuje Hamiltonian na součet Paulich operátorů.
To znamená, že výše uvedený přístup lze snadno přizpůsobit simulaci chemie.
Místo ručního přeskočíní všech Pauli podmínek v Jordan-Wigner reprezentaci je níže uveden jednoduchý příklad toho, jak by mohla tato simulace v rámci chemie vypadat.
Náš výchozí bod je [Jordánsko – Wigner kódování](xref:microsoft.quantum.chemistry.concepts.jordanwigner) Fermionic Hamiltonian, vyjádřené v kódu jako instance `JordanWignerEncoding` třídy.

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

Tento formát Jordánska – Wigner reprezentace, která je spotřební pro Q# algoritmy simulace, je uživatelsky definovaný typ `JordanWignerEncodingData` .
V nástroji Q# je tento formát předán funkci usnadnění `TrotterStepOracle` , která vrací operátor přibližného vývoje času pomocí Trotter – integrátor Suzuki, kromě dalších parametrů požadovaných pro jeho spuštění.

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

Důležité: Tato implementace používá několik optimalizací popsaných v [simulaci elektronické struktury Hamiltonians s využitím počítačů](https://arxiv.org/abs/1001.3855) s více procesory a [vylepšením](https://arxiv.org/abs/1403.1539) procesorových procesorů pro účely minimalizace počtu požadovaných rotací s jedním qubit, jakož i k omezení chyb simulace.

## <a name="qubitization"></a>Qubitization

Qubitization je alternativním přístupem k simulaci, která využívá nápady z kroků pro simulaci dynamiky.
I když qubitization vyžaduje více qubits než Trotter vzorce, metoda příslibů optimální škálování s časem vývoje a odolností proti chybám.
Z těchto důvodů se stala přizpůsobenou metodou pro simulaci Hamiltonian Dynamics v obecném a pro řešení potíží s elektronickými strukturami, konkrétně.

Na vysoké úrovni to qubitization provádí pomocí následujících kroků.
Nejdřív dejte $H = \ sum_j h_j H_j $ pro jednotkové a Hermitian $H _J $ a $h _j \ge $0.
Provedením dvojice odrazů qubitization implementuje operátor, který je ekvivalentní $ $W = e ^ {\Pm i \cos ^ {-1} (H/| h | _1)}, $ $ WHERE $ | H | _1 = \ sum_j | h_j | $.
Další krok zahrnuje transformaci eigenvalues operátoru průchodu z $e ^ {i\pm \cos ^ {-1} (E_k/| h | _1)} $, kde $E _k $ jsou eigenvalues $H $ to $e ^ {-iE_k t} $.
To je možné dosáhnout použitím celé řady metod transformace hodnot v jednotném provozu, včetně [zpracování signálu](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).

Případně, pokud jsou požadována pouze statická množství (například stavová energie Hamiltonian), pak bude stačit použít [odhad fáze](xref:microsoft.quantum.libraries.characterization) přímo na $W $ k odhadu energetické energie z výsledku pomocí kosinus výsledku.
To je důležité, protože umožňuje, aby se spektrální transformace prováděla klasickým způsobem namísto použití metody transformace hodnot na základě základu hodnoty.

Na podrobnější úrovni implementace qubitization vyžaduje dvě podrutiny, které poskytují rozhraní pro Hamiltonian.
Na rozdíl od metod Trotter – Suzuki jsou tyto podrutiny bez klasických procesorů a jejich implementace bude vyžadovat použití logarithmically více qubits, než by bylo nutné pro simulaci založenou na Trotter.

První podprogram počátečních operací, který qubitization používá, se nazývá $ \operatorname{Select} $ a je přislíbena, aby \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{Equation} kde každá $H _j $ se předpokládá jako Hermitian a jednotná.
I když se to může zdát být omezující, odvolat, že Pauli operátory jsou Hermitian a jednotná, takže aplikace, jako je například, nespadají do této architektury přirozeně.
Operace $ \operatorname{Select} $, třeba překvapivě, je ve skutečnosti operace reflexe.
To může být patrné ze skutečnosti, že $ \operatorname{Select} ^ 2 \ KET {j} \ket{\psi} = \ket{j} \ket{\psi} $, protože každá $H _j $ je jednotná a Hermitian a má tedy eigenvalues $ \Pm $1.

Druhá podrutina se nazývá $ \operatorname{Prepare} $.
Zatímco operace Select poskytuje prostředky pro soudržný přístup ke každému Hamiltonian podmínkám $H _j $ přípravná subrutina poskytuje metodu pro přístup k koeficientům $h _j $, \begin{Equation} \operatorname{Prepare}\ket {0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}.
\end{Equation} se pak pomocí brány řízených fází vynásobení zobrazuje $ $ \Lambda\ket {0} ^ {\otimes n} = \begin{Cases} \- \ket{x} & \Text{if} x = 0 \\\
        \ket{x} & \Text{Otherwise} \end{Cases}.
$$

Operace $ \operatorname{Prepare} $ se nepoužívá přímo v qubitization, ale místo toho se používá k implementaci reflexe o stavu, který $ \operatorname{Prepare} $ vytvoří $ $ \begin{align} R &amp; = 1-2 \ operátor {Prepare} \ket {0} \bra {0} \operatorname{Prepare} ^ {-1} \\ \\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^ {-1} .
\end{align} $ $

Operátor průchodu $W $, může být vyjádřený v souvislosti s $ \operatorname{Select} $ a $R $ Operations jako $ $ W = \operatorname{Select} R, $ $, který se znovu dá použít k implementaci operátoru, který je ekvivalentní (až do Isometry), do $e ^ {\Pm i \cos ^ {-1} (H/| h | _1)} $.

Tyto podrutiny se dají snadno nastavit v Q# .
Zvažte například jednoduché qubit příčné Ising Hamiltonian, kde $H = X_1 + X_2 + Z_1 Z_2 $.
V tomto případě Q# je kód, který implementuje operaci $ \operatorname{SELECT} $, vyvolán pomocí <xref:Microsoft.Quantum.Canon.MultiplexOperations> , zatímco operace $ \operatorname{Prepare} $ může být implementována pomocí <xref:Microsoft.Quantum.Preparation.PrepareArbitraryState> .
Příklad, který zahrnuje simulaci modelu Hubbard, najdete jako [ Q# vzorek](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard).

Ruční určení těchto kroků pro jakékoli problémy chemického složení by vyžadovalo mnohem úsilí, které se vyhne použití knihovny složení.
Podobně jako u algoritmu simulace Trotter-Suzuki výše `JordanWignerEncodingData` je předána funkci pohodlí `QubitizationOracle` , která vrací operátor Pass-spolu s dalšími parametry požadovanými pro jeho spuštění.

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

V důležitém případě <xref:Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle> je implementace platná pro libovolný Hamiltonians zadaný jako lineární kombinaci řetězců Pauli.
Verze optimalizovaná pro kochemii simulace je vyvolána pomocí <xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedQubitizationOracle> .
Tato verze je optimalizovaná tak, aby minimalizovala počet bran T, které využívají techniky popsané v tématu [kódování elektronických spektra v okruhech s lineárním T](https://arxiv.org/abs/1805.03662).
