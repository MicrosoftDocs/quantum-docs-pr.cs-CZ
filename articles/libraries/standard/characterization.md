---
title: 'Q # standardní knihovny – popis | Microsoft Docs'
description: 'Q # standardní knihovny – popis'
author: QuantumWriter
uid: microsoft.quantum.libraries.characterization
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: d77085aa8aa83c18858056bab1858d990efdb36e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185558"
---
# <a name="quantum-characterization-and-statistics"></a>Charakterizace a statistika stavových stavů #

Je důležité být schopné charakterizovat účinky operací, aby bylo možné vyvíjet užitečné algoritmy pro plnění.
To je náročné, protože každé měření systému doby využívání hodnot vychází z více bitů informací.
Aby se zjistilo, že se eigenvalue sám, může se stát, že se výsledky mnoha měření spojí dohromady, aby uživatel mohl glean spoustu informací potřebných k reprezentaci těchto konceptů.
Stavy nestavových stavů jsou obzvláště Vexing, protože [věta bez klonování](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) znamená, že neexistuje žádný způsob, jak zjistit libovolný stav z jedné kopie stavu, protože by to vedlo k vytváření kopií stavu.
Toto zmatení stavu nečinnosti od uživatele se projeví ve skutečnosti, že Q # nevystavuje nebo dokonce nedefinuje, k čemu *dochází* v programu.
Přiblížíme se k charakterizaci stavových polí tím, že se operace a stavy považují za černé. Tento přístup sdílí mnohem společné s experimentální praxí charakterizace, ověřování a ověřování (QCVV).

Popis je odlišný od mnoha dalších výše popsaných knihoven.
Účelem tohoto cíle je méně informací o klasickém informování o systému, a ne provádět jednotnou transformaci na vektoru stavu.
Tyto knihovny musí proto prolnout klasické i výpočetní zpracování informací.


## <a name="iterative-phase-estimation"></a>Odhad iterační fáze ##

Zobrazení doby plnění v programování v souvislosti s popisem doby použitelnosti naznačuje užitečnou alternativu k odhadu fáze.
To znamená, že místo přípravy $n $-qubit zaregistrovat, aby obsahovala binární reprezentaci fáze jako ve fázi odhadu doby platnosti, můžeme zobrazit odhad fáze jako proces, podle kterého se *klasický* agent učí vlastnosti systému v inventáři prostřednictvím jednotek.
V případě použití fáze Kickback se podíváme na velká a malá písmena, aby se v případě neznámého úhlu přepnuly aplikace černého pole na rotace. tím se ale změří ancilla qubit, který v každém kroku otočíte hned po otočení.
To má výhodu, že pro provedení fáze kickbacku, která je popsaná v případě případu, potřebujeme jenom jeden další qubit, jak se pak postupně učí fáze z výsledků měření v jednotlivých krocích.  
Každá z metod navrhovaných níže používá jinou strategii pro navrhování experimentů a různé metody zpracování dat pro učení fáze.  Každá z nich má jedinečné výhody od dodržování přísných chybových vazeb, k schopnostem začlenit předchozí informace, tolerovat chyby nebo spouštět na paměťově limitted klasických počítačích.

V diskuzi za iterativní fázi odhad budeme uvažovat o $U $, který je zadaný jako operace s černým polem.
Jak je popsáno v části pro Oracle v [datových strukturách](xref:microsoft.quantum.libraries.data-structures), Q # Canon odkazuje na operace <xref:microsoft.quantum.oracles.discreteoracle> uživatelsky definovaného typu, který je definovaný typem řazené kolekce členů `((Int, Qubit[]) => Unit : Adjoint, Controlled)`.
Pokud `U : DiscreteOracle`, `U(m)` implementuje $U ^ m $ pro `m : Int`.

V rámci této definice každý krok iterativní fáze odhadování pokračuje tím, že připraví auxillary qubit ve stavu $ \ket{+} $ spolu s počátečním stavem $ \ket{\phi} $, který předpokládáme, je [eigenvector](xref:microsoft.quantum.concepts.matrix-advanced) $U (m) $, tj. $U (m) \ket{\phi} = e ^ {im\phi} \ket{\phi} $.  
Pak se použije řízená aplikace `U(m)`, která připraví stav $ \left (R\_1 (m \phi) \ket{+} \right) \ket{\phi} $.
Stejně jako u případných jader je účinek kontrolované aplikace `U(m)` Oracle přesně stejný jako účinek použití $R _1 $ pro neznámou fázi na $ \ket{+} $, takže můžeme jednodušším způsobem popsat účinky $U $.
Volitelně algoritmus poté otočí ovládací prvek qubit pomocí $R _1 (-m\theta) $ k získání stavu $ \ket{\psi} = \left (R\_1 (m [\phi-\theta]) \ket{+} \right) \ket{\phi} $ $.
Auxillary qubit, který se používá jako ovládací prvek pro `U(m)`, se pak změří v $X $ základu a získá jednu z klasických `Result`.

V tomto okamžiku je rekonstrukce fáze z hodnot `Result` získaných pomocí iterativní fáze odhadu klasický problém při odvozování.
Hledání hodnoty $m $, která získala získané informace, s ohledem na pevnou odvozenou metodu, je jednoduše problémem ve statistice.
Zdůrazňujeme to tak, že stručně popisuje odhad iterativní fáze na teoretickou úroveň v parametru bayesovského rozhodování, který provede odhad formalit, než budete pokračovat v popisu statistických algoritmů, které jsou k dispozici v Q # Canon pro řešení tohoto klasického odvození. řešení.

### <a name="iterative-phase-estimation-without-eigenstates"></a>Odhad iterační fáze bez Eigenstates ###

Pokud je k dispozici vstupní stav, který není eigenstate, což znamená, že pokud $U (m) \ket{\phi\_j} = e ^ {im\phi\_j} $, proces odhadu fáze se nedeterministickém způsobem přesměruje na stav s jednou energií eigenstate.  Eigenstate, na který se nakonec konverguje, je eigenstate, který nejpravděpodobněji vyprodukuje pozorovanou `Result`.

Konkrétně jeden krok PE provádí následující nejednotnou transformaci stavu \begin{align} \sum_j \sqrt{\Pr (\phi\_j)} \ket{\phi\_j} \mapsto \sum\_j\frac {\ sqrt {\ PR (\phi\_j)} \sqrt{\Pr (\text{Result} | \ fí\_j)} \ket{\phi\_j}} {\sqrt{\Pr (\phi\_j) \sum\_j \Pr (\text{Result} | \phi\_j)}}.
\end{align} v případě, že se tento proces projde více hodnotami `Result`, eigenstates, které nemají maximální hodnoty $ \prod_k\Pr (\text{Result}\_k | \phi\_j) $, budou exponenciálně potlačeny.
V důsledku toho proces odvození bude v úmyslu v případě, že jsou experimenty zvoleni správně, sblížen do stavů s jediným eigenvalue.

Bayes ' věta dále navrhuje, že stav, který je výsledkem odhadu fáze, je zapsán ve tvaru \begin{align} \frac{\sqrt{\Pr (\phi\_j)} \sqrt{\Pr (\text{Result} | \phi\_j)} \ket{\phi\_j}} {\sqrt{\Pr (\phi\_j) \sum\_j \Pr (\text{Result} | \phi\_j)}} = \sum_j \sqrt{\Pr (\phi\_j | \text{Result})} \ket{\phi\_j}.
\end{align} sem $ \Pr (\phi\_j | \text{Result}) $ může být interpretted jako pravděpodobnost, že by jedna z předpokladů znamenala daný eigenstates:

1. znalosti stavu nestavení před měřením,
2. znalosti eigenstates $U $ a,
3. znalosti o eigenvalues $U $.

Učení těchto tří věcí je často exponenciálně pevně na klasickém počítači.
Nástroj odhadu fáze vzniká bez jakýchkoli malých rozsahů od faktu, že může provádět takovou úlohu učení s více částmi, aniž by bylo nutné znát jejich činnost.
Odhad fáze z tohoto důvodu se zobrazí v rámci řady algoritmů doby, které poskytují exponenciální urychlení.

### <a name="bayesian-phase-estimation"></a>Odhad fáze bayesovského rozhodování ###

> [!TIP]
> Další podrobnosti o odhadu fáze bayesovského rozhodování v praxi najdete v ukázce [**PhaseEstimation**](https://github.com/Microsoft/Quantum/tree/master/Samples/src/PhaseEstimation) .

Odhad fáze bayesovského rozhodování je jednoduchý.
Shromáždíte statistiku měření z protokolu odhadu fáze a potom výsledky zpracujete pomocí odvození bayesovského rozhodování a zadáním odhadu parametru.
Toto zpracování vám poskytne odhad eigenvalue a také nejistotu v tomto odhadu.
Umožňuje také provádět adaptivní experimenty a využívat předchozí informace.
Princip "principu" metod je, že je výpočetně náročný.

Chcete-li pochopit, jak tento proces odvození bayesovského rozhodování funguje, vezměte v úvahu případ zpracování jednoho `Zero`ho výsledku.
Všimněte si, že $X = \ket{+} \bra{+}-\ket{-}\bra{-}$, což znamená, že $ \ket{+} $ je jediným kladným eigenstateem $X $ odpovídajících `Zero`.
Pravděpodobnost pozorování `Zero` pro [`PauliX` měření](xref:microsoft.quantum.concepts.pauli) u prvního qubitu s ohledem na vstupní stav $ \ket{\psi}\ket{\phi} $ je tedy \begin{Equation} \Pr (\texttt{Zero} | \psi) = \left | \braket{+ | \psi} \right | ^ 2.
\end{Equation} v případě odhadu iterativní fáze máme to $ \ket{\psi} = R_1 (m [\phi-\theta]) \ket{+} $, například \begin{align} \Pr (\texttt{Zero} | \phi; m, \theta) & = \left | \braket{+ | R_1 (m [\phi-\theta]) | +} \right | ^ 2 \\\\ & = \left | \frac12 \left (\bra{0} + \bra{1} \right) \left (\ket{0} + e ^ {i m [\phi-\theta]} \ket{1} \right) \right | ^ 2 \\\\ & = \left | \frac{1 + e ^ {i m [\phi-\theta]}}{2} \right | ^ 2 \\\\ & = \cos ^ 2 (m [\phi-\theta]/2) \tag{★} \label{EQ: fáze-Est-pravděpodobnost}.
\end{align}, že odhad iterační fáze se skládá z učení četnosti kmitání funkce sinusovým, která umožňuje překlopit mince s posunem daným sinusoid.
Následující tradiční klasická terminologie volá $ \eqref{EQ: fáze-Est-pravděpodobnost} $ *pravděpodobnost* pro odhad iterativní fáze.

Zjistili jsme `Result` z pravděpodobnosti odhadu iterační fáze, můžeme pak použít pravidlo Bayes a určit, co by se mělo domnívat, že se má fáze sledovat.
Betonně \begin{Equation} \Pr (\phi | d) = \frac{\Pr (d | \phi) \Pr (\phi)} {\int \Pr (d | \phi) \Pr (\phi) {\mathrm d} \phi} \Pr (\phi), \end{Equation} kde $d \in \\{\texttt{Zero}, \texttt{One}\\} $ je `Result`a WHERE $ \Pr (\phi) $ Popisuje naše předchozí přesvědčení o $ \phi $.
To pak provede iterativní povýšení iterativní fáze odhadu, jako bezprostřední distribuce $ \Pr (\phi | d) $ popisuje naše přesvědčení hned po našem sledování dalšího `Result`.

V jakémkoli okamžiku tohoto postupu můžeme ohlásit fázi $ \hat{\phi} $ odvozenou klasickým kontrolérem jako \begin{Equation} \hat{\phi} \mathrel{: =} \expect [\phi | \Text{data}] = \int \phi \Pr (\phi | \Text{data}) {\mathrm d} \phi, \end{Equation}, kde $ \ text {data} $ představuje celý záznam všech získaných `Result`ch hodnot.

Přesné odvození bayesovského rozhodování je v praxi nevolatelné.
Pokud se chcete podívat na tento příklad, chtěli bychom se naučit $n $-bitovou proměnnou $x $.
Předchozí distribuce $ \Pr (x) $ podporuje více než $2 ^ n $ hypotetické hodnoty $x $.
To znamená, že pokud potřebujeme vysoce přesný odhad $xí, odhad fáze bayesovského rozhodování může vyžadovat nepotřebnou paměť a dobu zpracování.
I když některé aplikace, jako je například simulace provozu, limitted vyžaduje, že tyto metody nevylučuje jiné aplikace, jako je například algoritmus Shor, nemůže v rámci kroku odhadu fáze použít přesný odvozování bayesovského rozhodování.  Z tohoto důvodu poskytujeme implementace přibližných bayesovského rozhodování metod, jako je například [odhad fáze postupného procházení (RWPE)](xref:microsoft.quantum.research.randomwalkphaseestimation.randomwalkphaseestimation) , a také nebayesovského rozhodováníelné přístupy, jako je například [robustní odhad fáze](xref:microsoft.quantum.characterization.robustphaseestimation).

### <a name="robust-phase-estimation"></a>Robustní odhad fáze ###

Maximálně *dodatečná* bayesovského rozhodování rekonstrukce odhadu fáze z výsledků měření je exponenciálně těžká v nejhorším případě. Proto většina praktických výpočetních algoritmů při odhadu nevede ke snížení kvality v rámci rekonstrukce v systému Exchange pro množství klasického následného zpracování, které se místo toho škáluje podle počtu měření.

Jedním z takových příkladů s efektivním krokem po zpracování klasického zpracování je [spolehlivý algoritmus odhadu fáze](https://arxiv.org/abs/1502.02677)s jeho podpisem a vstupy uvedenými nahoře. Předpokládá, že vstupní $U $ se zabalí jako `DiscreteOracle` typ, a proto se jenom dotazují jenom celá čísla řízených $U $. Pokud je stav vstupu v registru `Qubit[]` eigenstate $U \ket{\psi} = e ^ {i\phi} \ KET {\ psí} $, algoritmus stabilní fáze odhadování vrátí odhad $ \hat{\phi}\in [-\pi, \pi) $ $ \phi $ jako `Double`.

Nejdůležitější funkcí odhadu robustní fáze, která je sdílena s většinou dalšími užitečnými variantami, je, že kvalita rekonstrukce $ \hat{\phi} $ je v některém smyslu Heisenberg – omezeno. To znamená, že pokud je odchylka $ \hat{\phi} $ od hodnoty true $ \sigma $, pak $ \sigma $ se škáluje v poměru k celkovému počtu dotazů $Q $ provedených na řízená – $U $, tj. $ \sigma = \mathcal{O} (1/Q) $. Nyní se definice odchylek liší mezi různými algoritmy odhadu. V některých případech to může znamenat, že s minimálně $ \mathcal{O} (1) $ pravděpodobností je chyba odhadu $ | \hat{\phi}-\phi |\_\circ\le \sigma $ u některé cyklické míry $ \circ $. U stabilního odhadu fáze je odchylka přesnější odchylkou $ \sigma ^ 2 = \mathbb{E}\_\hat{\phi} [(\mod\_{2 \ PI} (\hat{\phi}-\phi + \pi)-\pi) ^ 2] $, pokud rozbalíme pravidelné fáze do jednoho omezeného intervalu $ (-\pi, \pi] $. Směrodatná odchylka v robustním odhadu fáze je přesnější a splňuje hodnoty nerovnosti $ $ \begin{align} 2,0 \pi/Q \le \sigma \le 2 \ pi/2 ^ {n} \le 10.7 \ PI/Q, \end{align} $ $, kde dolní mez dosáhla limitu limitně velkých $Q $ a horní vázání je zaručeno i pro malé vzorky velikosti.  Všimněte si, že $n $ vybrané `bitsPrecision` vstupu, který implicitně definuje $Q $.

K dalším důležitým podrobnostem patří například malý počet režijních nákladů jenom $1 $ ancilla qubit, nebo že postup není adaptivní, což znamená, že požadovaná posloupnost experimentů na základě doby nezávisí na výsledcích mezilehlého měření. V tomto a nadcházejících příkladech, kde je důležité zvolit algoritmus odhadu fáze, by měl jedna z nich odkazovat na dokumentaci, jako je @"microsoft.quantum.canon.robustphaseestimation", a na odkazované publikace, kde najdete další informace a jejich implementaci.

> [!TIP]
> Existuje mnoho vzorků, ve kterých se používá robustní odhad fáze. V případě odhadu fáze při extrakci energie země s různými fyzickými systémy se podívejte na ukázku [ **simulace** ](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationCmdLine), [vzorek **SimpleIsing** ](https://github.com/Microsoft/Quantum/tree/master/Samples/src/SimpleIsing)a [ukázkový **model Hubbard** ](https://github.com/Microsoft/Quantum/tree/master/Samples/src/HubbardSimulation).


### <a name="continuous-oracles"></a>Kontinuální Oracle ###

Můžeme také zobecnit z výše uvedeného modelu Oracle, aby bylo možné používat v nepřetržitém případě Oracle modelované pomocí typu Canon <xref:microsoft.quantum.oracles.continuousoracle>.
Vezměte v úvahu, že místo jednoho jednotkového operátoru $U $ máme řadu $U operátorů \mathbb{R} (t) $ pro $t \in $, což $U (t) U (t) $ = $U (t + s) $.
Jedná se o slabší příkaz, než v samostatném případě, protože je možné vytvořit <xref:microsoft.quantum.oracles.discreteoracle> omezením $t = m\,\delta t $ pro některé pevné $ \delta t $.
[Věta na kámen](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups)– $U (t) = \exp (i H t) $ pro nějaký operátor $H $, kde $ \exp $ je exponenciální exponenciální, jak je popsáno v tématu [Pokročilé matrice](xref:microsoft.quantum.concepts.matrix-advanced).
Eigenstate $ \ket{\phi} $ of $H $, jako je $H \ket{\phi} = \phi \ket{\phi} $, pak také eigenstate $U (t) $ pro všechny $t $, \begin{Equation} U (t) \ket{\phi} = e ^ {i \phi t} \ket{\phi}.
\end{equation}

Přesnou stejnou analýzu, kterou popisuje [odhad fáze bayesovského rozhodování](#bayesian-phase-estimation) , lze použít a funkce pravděpodobnosti je pro tento obecnější model Oracle naprosto stejná: $ $ \Pr (\texttt{Zero} | \phi; t, \theta) = \cos ^ 2 \ Left (\frac{t [\phi-\theta]} @no__ t_1_ \right).
Pokud je navíc $U $ Simulace dynamického generátoru, stejně jako v případě [simulace Hamiltonian](xref:microsoft.quantum.libraries.applications#hamiltonian-simulation), budeme interpretovat $ \phi $ jako energii.
Proto použití fáze odhadu se souvislými dotazy nám umožní zjistit simulované [energetická spektrum molekul](https://arxiv.org/abs/quant-ph/0604193), [materiálů](https://arxiv.org/abs/1510.03859) nebo [polí teorie](https://arxiv.org/abs/1111.3633v2) bez nutnosti narušit náš výběr experimentů tím, že vyžaduje, $t $ jako celé číslo.

### <a name="random-walk-phase-estimation"></a>Odhad fáze náhodného procházení ###

Q # poskytuje užitečnou aproximaci odhadu fáze bayesovského rozhodování, která je navržena pro použití blízko u zařízení, která fungují s podmínkou náhodného procházení záznamu dat získaných z iterativní fáze odhadu.
Tato metoda je adaptivní i zcela deterministický a umožňuje téměř optimální škálování chyb v odhadovaných fázích $ \hat{\phi} $ s velmi nízkými náklady na paměť.

Protokol používá přibližnou bayesovského rozhodování odvozenou metodu, která předpokládá, že předchozí distribuce je Gaussovské.
Tento Gaussovské předpoklad umožňuje použití analytického vzorce pro experiment, který minimalizuje dodatečnou odchylku.
Algoritmus pak na základě výsledku tohoto experimentu posune odhad $ \phi $ vlevo nebo vpravo o předem stanovenou hodnotu a zmenší odchylku o předem stanovenou hodnotu.
Tato střední hodnota a variance poskytují všechny informace, které jsou nutné k zadání Gaussovské před $ \phi $ pro další experiment.
Neočekávaná selhání měření nebo skutečný výsledek počátečních částí předchozího postupu může způsobit selhání této metody.
Provede experimenty k testování, zda je aktuální střední hodnota a směrodatná odchylka vhodná pro systém.
Pokud nejsou, pak algoritmus provede inverzní krok procházení a proces pokračuje.
Možnost krokovat zpět také umožňuje, aby se algoritmus zjistil i v případě, že počáteční předchozí směrodatná odchylka je inapropriately malá.

## <a name="calling-phase-estimation-algorithms"></a>Algoritmy odhadu volání fáze ##

Každá operace odhadu fáze dodaná s Q # Canon používá jinou sadu vstupů Parametrizace kvality, kterou vydáváme z konečného odhadu $ \hat{\phi} $.
U těchto různých vstupů se ale sdílí několik běžných vstupů, takže částečná aplikace přes parametry kvality má za následek společný podpis.
Například operace <xref:microsoft.quantum.characterization.robustphaseestimation> popsaná v následující části má následující signaturu:

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

Vstup `bitsPrecision` je jedinečný pro `RobustPhaseEstimation`, zatímco `oracle` a `eigenstate` jsou společné.
Proto, jak je vidět v **H2Sample**, může operace přijmout algoritmus odhadu iterativní fáze se vstupním formulářem `(DiscreteOracle, Qubit[]) => Unit`, aby uživatel mohl zadat libovolné algoritmy odhadu fáze:

```qsharp
operation H2EstimateEnergy(
    idxBondLength : Int, 
    trotterStepSize : Double,
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double)) 
: Double
```

Tyto algoritmy odhadu fáze nesčetných jsou optimalizované pro různé vlastnosti a vstupní parametry, které je potřeba pochopit, aby se pro cílovou aplikaci zajistila nejlepší volba. Například některé algoritmy odhadu fází jsou adaptivní, což znamená, že budoucí kroky jsou classicně kontrolovány pomocí výsledků měření předchozích kroků. Některá z možností vyžadují, aby bylo možné exponentiate své černé části s jednotkou Oracle podle libovolných skutečných pravomocí, a jiné vyžadují jenom celočíselné pravomoci, ale dají se jenom vyřešit odhad fáze s hodnotou modulo $2 \ PI $. Některé vyžadují mnoho auxillarych qubits a další vyžadují jenom jeden.

Podobně použití odhadu náhodné fáze procházení pokračuje mnohem stejným způsobem jako u jiných algoritmů dodaných s Canon:

```qsharp
operation ExampleOracle(eigenphase : Double, time : Double, register : Qubit[]) : Unit
is Adj + Ctl {
    Rz(2.0 * eigenphase * time, register[0]);
}

operation BayesianPhaseEstimationCanonSample(eigenphase : Double) : Double {

    let oracle = ContinuousOracle(ExampleOracle(eigenphase, _, _));
    using (eigenstate = Qubit()) {
        X(eigenstate);
        // The additional inputs here specify the mean and variance of the prior, the number of
        // iterations to perform, how many iterations to perform as a maximum, and how many
        // steps to roll back on an approximation failure.
        let est = RandomWalkPhaseEstimation(0.0, 1.0, 61, 100000, 1, oracle, [eigenstate]);
        Reset(eigenstate);
        return est;
    }
}
```
