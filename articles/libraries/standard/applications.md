---
title: 'Aplikace v knihovně Q # Standard'
description: Seznamte se se dvěma základními aplikacemi ve výpočetním prostředí – Hamiltonian simulací a algoritmem hledání Shor.
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b7c46b634c6d691c067c0dd995301395408c85ca
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907218"
---
# <a name="applications"></a>Aplikace #

## <a name="hamiltonian-simulation"></a>Hamiltoniánská simulace ##

Simulace systémů pro plnění je jedním z nejzajímavějších aplikací výpočetních případů.
V klasickém počítači se při simulaci nenáročného navýšení na procesory škálují s dimenzí $N $ jeho reprezentace jeho stavu.
Vzhledem k tomu, že se tato reprezentace rozroste exponenciálně s počtem $n $ qubits $N = 2 ^ n $, což je známý známý také jako seznámení s [dimenzí](xref:microsoft.quantum.concepts.multiple-qubits), simulace nedostatku na klasický hardware je nevolatelné.

Nicméně tato situace může být velmi odlišná na hardwaru s nárokem na stav. Nejběžnější variace simulace nedostatku času se nazývá problém nezávisle na Hamiltonian simulace. K dispozici je jedna z popisů systému Hamiltonian $H $, což je Hermitian matice, a některé počáteční stavové stavy $ \ket{\psi (0)} $, které jsou v některých případech kódované v $n $ qubits v počítači s procesorem. V případě stavových stavů v uzavřených systémech se vyvíjí v rámci rovnice Schrödinger $ $ \begin{align} i\frac {d \ket{\psi (t)} {d t} & = H \ket{\psi (t)}, \end{align} $ $. cílem je implementovat dlouhodobý operátor pro vývoj času $U (t) = e ^ {-iHt} $ v nějakém pevném čase $t $ , kde $ \ket{\psi (t)} = U (t) \ket{\psi (0)} $ vyřeší rovnici Schrödinger.
Obdobně problém s simulací Hamiltonian závislé na čase vyřeší stejnou rovnici, ale s $H (t) $ nyní může být funkce času.

Simulace Hamiltonian je hlavní součástí mnoha dalších problémů s simulací doby plnění a řešení problémů s simulací Hamiltonian jsou algoritmy, které popisují sekvenci primitivních předpisů pro syntetizaci velkých a velkých a velkých procesorů $ \tilde{U} $ s chybou $\\| \tilde{U}-U (t)\\| \le \epsilon $ v [spektrální normě](xref:microsoft.quantum.concepts.matrix-advanced). Složitost těchto algoritmů závisí velmi silně na tom, jak je popis Hamiltonian zájmu přístupný pro počítač ve velkém počtu. Například v nejhorším případě, pokud $H $ v $n $ qubits byly poskytnuty jako seznam hodnot $2 ^ n \times 2 ^ n $, jeden pro každý prvek matice, jednoduše čtená data již vyžadují exponenciální čas. V nejlepším případě by jeden mohl předpokládat přístup k černému poli, který $O \ket{t}\ket{\psi (0)} = \ket{t}U (t) \ket{\psi (0)} $ triviální problém vyřeší. Ani jeden z těchto vstupních modelů není obzvlášť zajímavý – bývalé, protože není lepší než klasický přístup a druhá jako černý rámeček skrývá základní bránu své implementace, což může být exponenciální v počtu qubits.

### <a name="descriptions-of-hamiltonians"></a>Popisy Hamiltonians ###

Jsou proto vyžadovány další předpoklady formátu vstupu. Jemné vyvážení musí být prolomeno mezi vstupními modely, které jsou dostatečně popisné, aby zahrnovaly zajímavé Hamiltonians, jako jsou například pro reálné fyzické systémy nebo zajímavé výpočetní problémy, a vstupní modely, které jsou dostatečně omezující. aby bylo možné je efektivně implementovat na počítač s nárokem na více počítačů. V této literatuře se může najít celá řada netriviálních vstupních modelů a jejich rozsah od až po klasický. 

Jako příklad u vstupních modelů pro [procesory předpokládá Hamiltonian simulace](http://www.nature.com/articles/s41534-017-0013-7) přístup k operacím s černým přístavem, který vytváří kopie matrice hustoty $ \rho $, které se považují za Hamiltonian $H $. [V jednom z](https://arxiv.org/abs/1202.5822) nich předpokládáme, že Hamiltonian místo toho předává součet unitaries $ $ \begin{align} H & = \sum ^ {d-1}\_{j = 0} a\_j \hat{U}\_j, \end{align} $ $, kde $a\_j > 0 $ jsou a $ \hat{U}\_j $ jsou unitaries. Pak se předpokládá, že má k dispozici černý přístup k jednotkám Oracle $V = \sum ^ {d-1}\_{j = 0} \ket{j}\bra{j}\otimes \hat{U}\_j $, která vybere požadované $ \hat{U}\_j $, a Oracle $A \ket{0}= \sum ^ {d-1}\_{j = 0} \sqrt{a\_j/\ suma ^ {d-1}\_{k = 0} \Alpha\_j} \ket{j} $, které vytvářejí tyto koeficienty pro kódování stavových procesorů. V případě [simulace zhuštěných Hamiltonian](https://arxiv.org/abs/quant-ph/0301023)se předpokládá, že Hamiltonian je zhuštěná matice s pouze $d = \mathcal{O} (\Text{polylog} (N)) $ nenulového prvku v každém řádku. Kromě toho předpokládá, že existence efektivních okruhů na více procesorech vychází z umístění těchto nenulových prvků, jakož i jejich hodnot. Složitost [algoritmů simulace Hamiltonian](xref:microsoft.quantum.more-information) je vyhodnocována v podobě počtu dotazů do těchto černých polí a základní složitost brány pak závisí hodně na obtížnosti implementace těchto černých polí.

> [!NOTE]
> Notaci Big-O se běžně používá k popisu škálování algoritmů složitosti algoritmů. Zadané dvě reálné funkce $f, g $, výraz $g (x) = \mathcal{O} (f)) $ znamená, že existuje absolutní kladná konstanta $x\_0, c > 0 $, což $g (x) \le c f (x) $ pro všechny $x \ge x\_$0. 

U většiny praktických aplikací, které se mají implementovat na počítač s procesorem, musí být tato černá pole efektivně implementovaná, tedy s využitím \Text{polylog} (N) $ \mathcal{O} (N) $ primitivních procesorů. Mnohem silné a efektivní simulable Hamiltonians musí mít nějaký dostatečně zhuštěný klasický popis. V jednom takovém složení se předpokládá, že Hamiltonian dekládá do součtu Hermitian částí $ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j.
\end{align} $ $ navíc předpokládá, že každá část, Hamiltonian $H\_j $, se dá snadno simulovat. To znamená, že jednotková $e ^ {-iH\_j t} $ se dá $t kdykoli implementovat přesně pomocí $ \mathcal{O} (1) $ primitivních procesorových vratek. To je například pravda ve speciálním případě, kdy každá $H\_j $ jsou místní operátory Pauli, což znamená, že jsou tensor produkty $ \mathcal{O} (1) $ Pauli operátory, které nepatří do identity, které fungují na prostorovém uzavírání qubits. Tento model je vhodný zejména pro fyzické systémy s ohraničenou a místní interakcí, protože počet podmínek je $d = \mathcal{O} (\Text{polylog} (N)) $, a může být jasně zapsán, tj. klasickým způsobem popsaným v době polynomu.

> [!TIP]
> Hamiltonians, které se rozloží na součet částí, mohou být popsány pomocí dynamické knihovny reprezentace generátoru. Další informace najdete v části reprezentace dynamického generátoru v [datových strukturách](xref:microsoft.quantum.libraries.data-structures).

### <a name="simulation-algorithms"></a>Algoritmy simulace ###

Algoritmus pro simulaci doby provozu Převede daný popis Hamiltonian na sekvenci primitivních procesorových vratů, které jsou v rámci celého přibližného vývoje času pomocí zmíněného Hamiltonian.

Ve speciálním případě, kdy Hamiltonian založí do součtu Hermitian částí, je dekompozice Trotter-Suzuki obzvláště jednoduchý a intuitivní algoritmus pro simulaci Hamiltonians, která se rozloží na součet Hermitian komponent. Například první vydaný integrátor této rodiny je přibližně $ $ \begin{align} U (t) & = \left (e ^ {-iH\_0 t/r} e ^ {-iH\_1 t/r} \cdots e ^ {-iH\_{d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j\\| H\_j\\| ^ 2 t ^ 2/r), \end{align} $ $ s použitím produktu $r d $ terms. 

> [!TIP]
> V ukázkách jsou pokryté aplikace algoritmu simulace Trotter-Suzuki.
> Pro model Ising s využitím pouze vnitřních operací, které jsou k dispozici v každém cílovém počítači, se podívejte na [ukázku **SimpleIsing** ](https://github.com/microsoft/Quantum/blob/master/samples/simulation/ising/simple).
> Pro model Ising pomocí struktury ovládacích prvků knihovny Trotter-Suzuki se podívejte na [ukázku **IsingTrotter** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/trotter-evolution).
> Pro molekulovou vodík pomocí struktury ovládacího prvku knihovna Trotter-Suzuki se podívejte na [ukázku **simulace H2** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line).

V mnoha případech bychom chtěli implementovat algoritmus simulace, ale neuvažujete o jeho implementaci. Například integrátor druhého řádu se blíží $ $ \begin{align} U (t) & = \left (e ^ {-iH\_0 t/2R} e ^ {-iH\_1 t/2R} \cdots e ^ {-iH\_{d-1} t/2R} e ^ {-iH\_{d-1} t/2R} \cdots e ^ {-iH\_1 t/2R} e ^ {-iH\_0 t/2R} \right) ^ {r} + \mathcal{O} (d ^ 3 \ max_j\\| H\_j\\| ^ 3 t ^ 3/r ^ 2), \end{align} $ $ za použití podmínek $2RD $. Větší objednávky budou zahrnovat ještě víc podmínek a optimalizované varianty můžou pro exponenciální hodnoty vyžadovat vysoce triviální řazení. Další pokročilé algoritmy můžou také zahrnovat použití ancilla qubits v rámci mezipostupných kroků. Proto se jako uživatelsky definovaný typ zabalí algoritmy simulace ve Canon.

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

První parametr `Double` je čas simulace, druhý parametr `EvolutionGenerator`, který je popsán v části dynamické reprezentace generátoru [datových struktur](xref:microsoft.quantum.libraries.data-structures), je klasický popis Hamiltonian zabaleného času s pokyny, jak mohou být jednotlivé podmínky v Hamiltonian simulované okruhem. Typy tohoto formuláře se blíží jednotkové operaci $e ^ {-iHt} $ na třetím parametru `Qubit[]`, což je registr, který ukládá stav nečinnosti simulovaného systému. Podobně jako v případě závislého na čase definujeme místo toho uživatelem definovaný typ s typem `EvolutionSchedule`, což je klasický popis Hamiltonian závislého na čase.

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

Jako příklad může být dekompozice Trotter-Suzuki volána pomocí následujících funkcí Canon s parametry `trotterStepSize` úpravou délky simulace v každé exponenciální a `trotterOrder` pro pořadí požadovaného integrátoru.

```qsharp
function TrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: SimulationAlgorithm {
    ...
}

function TimeDependentTrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: TimeDependentSimulationAlgorithm {
    ...
}
```

> [!TIP]
> Aplikace knihovny simulace jsou pokryté v ukázkách. V případě odhadu fáze v modelu Ising pomocí `SimulationAlgorithm`se podívejte na [ukázku **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).
> Pro přípravu stavu adiabatic v modelu Ising pomocí `TimeDependentSimulationAlgorithm`se podívejte na [ukázku **AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).


### <a name="adiabatic-state-preparation--phase-estimation"></a>Odhad stavu Adiabatic & fáze ###

Jednou z běžných aplikací simulace Hamiltonian je adiabatic stavový přípravek. V takovém případě je k dispozici se dvěma Hamiltonians $H\_{\Text{Start}} $ a $H\_{\Text{end}} $ a stavovou hodnotu $ \ket{\psi (0)} $, což je základní stav spouštěcího Hamiltonian $H\_{\Text{Start}} $. Obvykle je zvolena možnost $H\_{\Text{Start}} $, což znamená, že $ \ket{\psi (0)} $ se snadno připravuje z výpočetního stavu na výpočetní úrovni $ \ket{0\cdots 0} $. Díky interpolaci mezi těmito Hamiltoniansy v případě problémů s simulací závislé na čase je možné ukončit s vysokou pravděpodobností v zemi konečného stavu Hamiltonian $H\_{\Text{end}} $. I když Příprava dobrých odhadů na Hamiltonian země by mohla tímto způsobem probíhat voláním algoritmů simulace Hamiltonian, které jsou závislé na čase, jako dílčí rutina, dalších koncepčních různých přístupů, jako je variace. eigensolver je možné.

Ještě další všudypřítomný aplikace v chemii v terénu odhaduje stavovou energii Hamiltonians, která představuje mezilehlé kroky chemické reakce. Takové schéma může například spoléhat na přípravu stavu adiabatic, aby vytvořilo základní stav a pak zahrnulo nezávislá časová simulace Hamiltonian jako dílčí rutinu v popisu fáze odhadu pro extrakci této energie s určitou konečnou chybou a pravděpodobnost úspěchu 

Abstrakce algoritmů simulace jako uživatelsky definovaných typů `SimulationAlgorithm` a `TimeDependentSimulationAlgorithm` nám umožňuje pohodlně začlenit jejich funkce do výkonnějších procesorových algoritmů. To nám motivuje pro tyto běžně používané podrutiny.

Proto definujeme pohodlnou funkci

```qsharp
function InterpolatedEvolution(
        interpolationTime : Double, 
        evolutionGeneratorStart : EvolutionGenerator,
        evolutionGeneratorEnd : EvolutionGenerator,
        timeDependentSimulationAlgorithm : TimeDependentSimulationAlgorithm)
: (Qubit[] => Unit is Adj + Ctl) {
        ...
}
 
```

Vrátí se tak jednotná operace, která implementuje všechny kroky adiabatic stavu. První parametr `interpolatedTime` definuje čas, ve kterém se lineárně interpoluje mezi počátečními Hamiltonian popsanými druhým parametrem `evolutionGeneratorStart` a koncovým Hamiltonianem popsaným třetím parametrem `evolutionGeneratorEnd`. Čtvrtý parametr `timeDependentSimulationAlgorithm` je tam, kde jedna umožňuje výběr algoritmu simulace. Všimněte si, že pokud je `interpolatedTime` dostatečně dlouho, počáteční stavový stát zůstane okamžitým stavem Hamiltonian po celou dobu trvání simulace závislé na čase, a tak končí v uzemněném stavu koncového Hamiltonian.

Také definujeme užitečnou operaci, která automaticky provádí všechny kroky typického experimentu pro práci s více operačními systémem. Například máme následující, které vrací odhad energie stavu, který vytvořila Příprava stavu adiabatic:

```qsharp
operation EstimateAdiabaticStateEnergy(
    nQubits : Int,
    statePrepUnitary : (Qubit[] => Unit),
    adiabaticUnitary : (Qubit[] => Unit),
    qpeUnitary: (Qubit[] => Unit is Adj + Ctl),
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double {
...
}
```

`nQubits` je počet qubits, který se používá ke kódování počátečního stavu. `statePrepUnitary` připraví počáteční stav z výpočetního základu $ \ket{0\cdots 0} $. `adiabaticUnitary` je jednotná operace, která implementuje přípravu stavu adiabatic, například vytvořenou funkcí `InterpolatedEvolution`. `qpeUnitary` je jednotná operace, která se používá k provádění odhadu fáze ve výsledném stavu nečinnosti. `phaseEstAlgorithm` je naše volba algoritmu odhadu fází.

> [!TIP]
> V ukázkách jsou pokryté aplikace adiabatic State Preparation. Pro model Ising pomocí ruční implementace přípravných stavů adiabatic a pomocí funkce `AdiabaticEvolution` se podívejte na [ukázku **AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).
> V případě odhadu fáze a přípravy stavu adiabatic v modelu Ising se podívejte na [ukázku **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).

> [!TIP]
> [Simulace molekulové vodíku](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line) je zajímavá a krátká ukázka. Model a experimentální výsledky hlášené v [O'Malley et. Al.](https://arxiv.org/abs/1512.06860) vyžaduje jenom Pauli matice a má ve tvaru $ \hat H = g\_{0}I\_0I\_1 + g\_1 {Z\_0} + g\_2 {Z\_1} + g\_3. {Z\_0} {Z\_1} + g\_4 {Y\_0} {Y\_1} + g\_5 {X\_0} {X\_1} $. Jedná se o efektivní Hamiltonian, který vyžaduje jenom 2 qubits, kde se konstanty $g $ vypočítávají z vzdálenosti $R $ mezi dvěma atomy vodíku. Pomocí funkcí Canon se Pauls převede na unitaries a pak se postupně vyvinuly v krátkém časovém úseku pomocí dekompozice Trotter-Suzuki. Dobrý odhad stavu $H _2 $ uzemnění se dá vytvořit bez použití přípravy stavu adiabatic, takže se stavová energie může najít přímo pomocí odhadu fáze z Canon.

## <a name="shors-algorithm"></a>Shorův algoritmus ##
Shor algoritmus zůstává jedním z nejvýznamnějších vývojů ve výpočetním prostředí, protože ukázalo, že by se počítače mohly použít k řešení důležitých, aktuálně nerušivých problémů.
Algoritmus Shor poskytuje rychlý způsob, jak rychle vyhodnotit Velká čísla pomocí počítače s velkým množstvím, což je problém s názvem *faktoringu*.
Zabezpečení mnoha současných cryptosystemsch dnů vychází z předpokladu, že pro účely faktoringu neexistuje žádný rychlý algoritmus.
Proto má Shorový algoritmus v podstatě vliv na zabezpečení v rámci po celém světě.

Shor algoritmus lze představit jako hybridní algoritmus.
Počítač s více tečkami slouží k provádění výpočetně náročného úkolu, který se označuje jako perioda hledání.
Výsledky hledání za období jsou následně zpracovávány Classic za účelem odhadu faktorů.
Tyto dva kroky prozkoumáme níže.

### <a name="period-finding"></a>Hledání období ###

Zjistili jsme, jak funkce Fourierova transformace a odhad fáze funguje (viz [algoritmy](xref:microsoft.quantum.libraries.standard.algorithms)doby provozu), můžeme pomocí těchto nástrojů vyřešit klasický pevný výpočetní problém nazývaný *hledání období*.  V další části se dozvíte, jak použít hledání období pro faktoring.

Zadaná dvě celá čísla $a $ a $N $, kde $a < N $, cílem hledání období, označovaného také jako hledání objednávek, je najít _objednávku_ $r $ z $a $ modulo $N $, kde $r $ je definováno jako nejmenší kladné celé číslo tak, aby $a ^ r \equiv 1 \Text{mod} N $.  

Pokud chcete zjistit pořadí pomocí počítače s více poli, můžeme použít algoritmus odhadu fáze použitý u následujícího operátoru s jednou jednotkou $U _a $: $ $ U_a \ket{x} \equiv \ket{(AX) \Text{mod} N}. $ $ eigenvectors $U _a $ jsou pro celočíselné $s $ a $0 \ LEQ s \leq r-$1, $ $ \ket{x_s} \equiv 1/\sqrt{r} \sum\_{k = 0} ^ {r-1} e ^ {\frac{-2\pi i SK} {r}} \ket{a ^ k\text {mod} N}, $ $ jsou _eigenstates_ $U _a $.
Eigenvalues $U _a $ $ U\_\ket{x\_s} = e ^ {2 \ PI i s/r} \ket{x\_s}. $$

Odhad fáze tak má za výstupem eigenvalues $e ^ {2 \ PI i/r} $, z nichž lze $r $ zjistit efektivně pomocí dalších [zlomků](https://en.wikipedia.org/wiki/Continued_fraction) z $s/r $.

Diagram okruhu pro zjištění doby trvání:

![Diagram okruhu pro hledání doby trvání](./../../media/QPE.svg)

Zde $2N $ qubits jsou inicializovány do $ \ket{0}$ a $n $ qubits jsou inicializovány do $ \ket{1}$.
Čtenář se znovu může zajímat, proč se v registru eigenstates inicializuje do $ \ket{1}$.
Vzhledem k tomu, že jedna z těchto informací neví, že pořadí $r $ předem nemůžeme přímo připravit stavy $ \ket{x_s} $.
Donovanovo, zapíná se $1/\ sqrt {r} \sum\_{s = 0} ^ {r-1} \ket{x\_s} = \ket{1}$.
Nemusíte ve skutečnosti připravovat $ \ket{x} $!
Můžeme pouze připravit registraci $n $ qubits ve stavu $ \ket{1}$. 

Okruh obsahuje QFT a několik řízených bran.
Brána QFT byla popsána [dříve](xref:microsoft.quantum.libraries.standard.algorithms).
Řízená $U _a $ \ket{x} $ to $ \ket{(AX) \Text{mod} N} $, pokud je ovládací prvek qubit $ \ket{1}$ a map $ \ket{x} $ na $ \ket{x} $, jinak.

Pokud chcete dosáhnout $ (a ^ NX) \Text{mod} N $, můžeme jednoduše použít řízené $U _ {a ^ N} $, kde vypočítáme $a ^ n \Text{mod} N $ Classic, aby se mohl připojit k okruhu.  
Okruhy, které by se dosáhly těchto modulárních aritmetických výpočtů, jsou popsané v [aritmetické dokumentaci](./algorithms.md#arithmetic)pro procesory, konkrétně vyžadujeme modulární okruh umocnění k implementaci $U\_{a ^ i} $.

Zatímco okruh výše odpovídá [odhadu fáze](xref:microsoft.quantum.characterization.quantumphaseestimation) plnění a explicitně povoluje hledání objednávek, můžeme snížit počet požadovaných qubits. Můžeme buď použít metodu Beauregard pro hledání objednávek, jak je popsáno [na stránce 8 arXiv: quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8), nebo použijte jednu z rutin odhadu fáze, která je k dispozici v Microsoft. Například [robustní odhad fáze](xref:microsoft.quantum.characterization.robustphaseestimation) také používá jednu další qubit.
 
### <a name="factoring"></a>Které budou zohledňovat ###
Cílem faktoringu je určit dva základní faktory typu Integer $N $, kde $N $ je $n číslo bitu.  
Sefaktoringování se skládá z kroků popsaných níže. Kroky jsou rozděleny do tří částí: rutina klasického předzpracování (1-4); výpočetní rutina pro vyhledá pořadí $a \Text{mod} N $ (5); a klasická rutina postprocessing, která odvozuje základní faktory od pořadí (6-9).

Rutina pro klasický proces předzpracování se skládá z následujících kroků:
1. Je-li $N $ je dokonce, vraťte se do základního faktoru $2 $.
2. Pokud $N = p ^ q $ pro $p \geq1 $, $q \geq2 $, vraťte se do základního faktoru $p $.  Tento krok se provádí v klasickém nasazení.
3. Vyberte náhodné číslo $a $, které $1 < < N-$1.
4. Pokud $ \Text{GCD} (a, N) > 1 $, vraťte se k hlavnímu faktoru $ \Text{GCD} (a, N) $. Tento krok je vypočítán pomocí algoritmu euklidovského.
Pokud se nevrátí žádný základní faktor, budeme pokračovat v rutině pro nečinnosti:
5. Pro výpočet pořadí $r $ of $a \Text{mod} N $ zavolejte algoritmus pro zjištění doby platnosti. Pomocí $r $ v klasické rutině postprocessing určete základní faktory:
6. Pokud je $r $ liché, vraťte se k kroku předběžného zpracování (3).
7. Pokud je $r $ i $a ^ {r/2} =-1 \ text {mod} N $, vraťte se zpátky na krok předběžného zpracování (3).
8. Pokud $ \Text{GCD} (a ^ {r/2} + 1, N) $ je netriviální faktor $N $, vraťte $ \Text{GCD} (a ^ {r/2} + 1, N) $.
9. Pokud $ \Text{GCD} (a ^ {r/2}-1, N) $ je netriviální faktor $N $, vraťte $ \Text{GCD} (a ^ {r/2}-1, N) $.


Algoritmus faktoringu je pravděpodobnostní: může se zobrazit, že s pravděpodobností nejméně jednu polovinu, která $r $ bude i $a ^ {r/2} \neq-1 \Text{mod} N $, čímž se vytvoří základní faktor.  (Další [informace](xref:microsoft.quantum.more-information)najdete v části [původní dokument Shor](https://doi.org/10.1109/SFCS.1994.365700) nebo v části *základní výpočetní* texty v tématu.)
Pokud se nevrátí žádný primární faktor, jednoduše zopakujeme algoritmus z kroku (1).  Po $n $ pokusů se pravděpodobnost, že se všechny pokusy nezdařila, nanejvýš na 2 ^ {-n} $.
Proto po opakování algoritmu malý počet pokusů o úspěch je prakticky zaručený.
