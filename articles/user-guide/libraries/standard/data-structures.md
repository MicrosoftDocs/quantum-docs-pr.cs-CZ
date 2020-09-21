---
title: Datové struktury ve Q# standardních knihovnách
description: Přečtěte si o datových strukturách, Oracle a dynamických generátorech ve Q# standardních knihovnách společnosti Microsoft.
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 51eb52d0b8ace972f6a425edba400ca9a8916d2e
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835583"
---
# <a name="data-structures-and-modeling"></a>Datové struktury a modelování #

## <a name="classical-data-structures"></a>Klasické datové struktury ##

Společně s uživatelsky definovanými typy pro reprezentaci konceptů, Canon také poskytuje operace, funkce a typy pro práci s klasickými daty používanými v řízení systémů.
Například <xref:microsoft.quantum.arrays.reversed> funkce přebírá pole jako vstup a vrací stejné pole v opačném pořadí.
To lze potom použít pro pole typu `Qubit[]` , abyste se vyhnuli nutnosti použít nepotřebné brány $ \operatorname{swap} $ při konverzi mezi reprezentací typu Integer.
Podobně jsme viděli v předchozí části, že typy formuláře `(Int, Int -> T)` mohou být užitečné, aby představovaly kolekce s náhodným přístupem, takže <xref:microsoft.quantum.arrays.lookupfunction> funkce poskytuje pohodlný způsob, jak vytvořit takové typy z typů polí.

### <a name="pairs"></a>Spár ###

Canon podporuje zápis funkčního stylu pro páry, doplnění přístupu k řazeným kolekcím členů pomocí dekonstrukce:

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a>Pole ###

Canon nabízí několik funkcí pro manipulaci s poli.
Tyto funkce jsou typu parametrizované, a proto je lze použít s poli libovolného Q# typu.
Například <xref:microsoft.quantum.arrays.reversed> funkce vrátí nové pole, jehož prvky jsou v opačném pořadí, od vstupu.
Dá se použít ke změně způsobu, jakým se při volání operací reprezentuje registr s hodnotou:

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

Podobně <xref:microsoft.quantum.arrays.subarray> lze funkci použít k přeuspořádání nebo přeřazení podmnožiny prvků pole:

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

V kombinaci s řízením toku může funkce manipulace s polem, jako je například, <xref:microsoft.quantum.arrays.zip> poskytovat účinný způsob, jak vyjádřit programy na více než jednou.

```qsharp
// Applies X₃ Y₁ Z₇ to a register of any size.
ApplyToEach(
    ApplyPauli(_, register),
    Map(
        EmbedPauli(_, _, Length(register)),
        Zip([PauliX, PauliY, PauliZ], [3, 1, 7])
    )
);
```

## <a name="oracles"></a>Oracle ##

Ve [fázi odhadu](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) a [amplitudy zesílení amplitudy](https://en.wikipedia.org/wiki/Amplitude_amplification) se pojem Oracle objevuje často.
V tomto případě se pojem Oracle vztahuje na podprogramovou rutinu Blackbox, která funguje na sadě qubits, a vrátí odpověď jako fázi.
Tato podrutina se často může považovat za vstup do algoritmu pro plnění hodnoty, který přijímá Oracle, kromě některých dalších parametrů a používá řadu operací po sobě a zpracovává volání této podprocesu, jako by šlo o základní bránu.
Aby bylo možné skutečně implementovat větší algoritmus, je nutné poskytnout konkrétní rozložené rozhraní Oracle do základních bran, ale takové rozložené není nutné, aby bylo možné pochopit algoritmus, který volá Oracle.
V Q# nástroji je tato abstrakce reprezentována pomocí těchto operací jsou hodnoty první třídy, což znamená, že operace mohou být předány do implementace algoritmů pro plnění v černém poli.
Kromě toho uživatelsky definované typy se používají k označení různých reprezentace Oracle bezpečným způsobem, což ztěžuje náhodné rozlišit různé druhy operací černého boxu.

Tyto Oracle se zobrazují v řadě různých kontextů, včetně slavnýchch příkladů, jako jsou například [Grover vyhledávání](https://en.wikipedia.org/wiki/Grover%27s_algorithm) a simulace.
Tady se zaměříme na Oracle, které potřebuje jenom dvě aplikace: zesílení amplitud a odhad fáze.
Před pokračováním odhadu fáze budeme nejdřív projednávat amplituda zesílení Oracle.

### <a name="amplitude-amplification-oracles"></a>Amplituda zesílení pro Oracle ###

Algoritmus zesílení amplitudy se zaměřuje na otočení mezi počátečním stavem a konečným stavem, a to použitím sekvence odrazů stavu.
Aby algoritmus fungoval, potřebuje specifikace obou těchto stavů.
Tyto specifikace jsou dány dvěma Oracle.
Tyto Oracle fungují tak, že jsou porušují vstupy na dvou místech a "cílový" prostor a "počáteční" prostor.
Oracle identifikují taková dílčí místa, podobně jako Pauli operátory identifikují dva mezery, a to tak, že na tyto prostory použijí fázi $ \Pm $1.
Hlavní rozdíl spočívá v tom, že tyto prostory nemusí být v této aplikaci v polovičním prostoru.
Všimněte si také, že tyto dvě podprostory nejsou obvykle vzájemně exkluzivní: budou existovat vektory, které jsou členy obou prostorů.
Pokud to neplatí, pak amplituda zesílení by neměla mít žádný vliv, takže potřebujeme, aby počáteční dílčí prostor byl bez nulového překrytí cílovým podprostorem.

Všimněte si, že první Oracle, který potřebujeme pro zesílení amplitud, musí být $P \_ $0, definovaná pro následující akce.  Pro všechny stavy $ \ket{x} $ v "počátečním" podprostoru $P \_ 0 \ket{x} =-\ket{x} $ a pro všechny stavy $ \ket{y} $, které nejsou v tomto dílčím prostoru, máme $P \_ 0 \ket{y} = \ket{y} $.
Oracle, který označuje cílové podprostor, $P _1 $, používá přesně stejný tvar.
Pro všechny stavy $ \ket{x} $ v cílovém dílčím prostoru (tj. pro všechny stavy, které chcete algoritmus výstup), $P _1 \ KET {x} =-\ket{x} $.
Podobně platí pro všechny stavy $ \ket{y} $, které nejsou v cílovém místě $P _1 \ KET {y} = \ket{y} $.
Tyto dvě odrazy se pak zkombinují za účelem vytvoření operátoru, který vydává jediný krok zesílení amplitud, $Q =-P_0 P_1 $, kde se celkový symbol mínus považuje jenom v kontrolovaných aplikacích.
Amplituda amplitud pak pokračuje tím, že vezme počáteční stav $ \ket{\psi} $, který je v počátečním a pak provede $ \ket{\psi} \mapsto Q ^ m \ket{\psi} $.
Tato iterace zaručuje, že pokud jeden začíná s počátečním stavem, který překrývá $ \sin ^ 2 (\theta) $ s označeným prostorem, pak po $m $ iterace se překrývá na $ \sin ^ 2 ([2 min + 1] \theta) $.
Proto si obvykle přejete zvolit $m $ jako bezplatný parametr, například $ [2 min + 1] \theta = \ pi/2 $; Takové tuhé volby ale nejsou důležité pro některé formy zesílení amplitud, jako je zesílení amplitudy pevně stanovených bodů.
Tento proces nám umožňuje připravit stav ve vyhrazeném místě pomocí kvadratických méně dotazů na funkci označení a funkce přípravy stavu, než by bylo možné na čistě klasických zařízeních.
To je důvod, proč je zesílení amplitud flexibilní stavební blok pro spoustu aplikací, které výpočetní výkon využívá.

Aby bylo možné pochopit, jak používat algoritmus, je užitečné poskytnout příklad, který poskytuje konstrukci Oracle.  V tomto nastavení zvažte, jak provést Grover algoritmus pro prohledávání databáze.
V hledání Grover je cílem transformovat stav $ \ket{+} ^ {\otimes n} = H ^ {\otimes n} \ket {0} $ na jeden z (potenciálně) mnoho označených stavů.
Abychom mohli ještě víc zjednodušit, Podívejme se jenom na případ, kde je jenom označený stav $ \ket {0} $.
Pak máme návrh dvou Oracle: ten označuje pouze počáteční stav $ \ket{+} ^ {\otimes n} $ s znaménkem mínus a další, který označuje označený stav $ \ket {0} $ znaménkem mínus.
Druhou bránu je možné implementovat pomocí následující operace zpracování pomocí operací toku řízení v Canon:

```qsharp
operation ReflectAboutAllZeros(register : Qubit[]) : Unit 
is Adj + Ctl {

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);

    // Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.
    // This gate will lead to a sign flip if and only if every qubit is
    // $1$, which happens only if each of the qubits were $0$ before step 1.
    Controlled Z(Most(register), Tail(register));

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);
}
```

Tento Oracle je pak zvláštním případem <xref:microsoft.quantum.canon.rall1> operace, který umožňuje otočení pomocí libovolné fáze namísto případu odrazu $ \phi = \pi $.
V tomto případě `RAll1` se podobá <xref:microsoft.quantum.intrinsic.r1> operaci předehru, a to v tom, že se místo \ket{11\cdots1}ého stavu qubit $ \ket $ otáčí o $ $ {1} .

Oracle, který označuje počáteční mezeru, může být vytvořen podobně.
V pseudokódu:

1. U každého qubit použijte $H $ bran.
2. U každého qubit použijte $X $ bran.
3. Pro $n ^ {\Text{th}} $ qubit použijte bránu $Z $-$1 řízenou v $n.
4. U každého qubit použijte $X $ bran.
5. U každého qubit použijte $H $ bran.

V tuto chvíli jsme také předvedli použití <xref:microsoft.quantum.canon.applywith> společně s <xref:microsoft.quantum.canon.rall1> výše popsanou operací:

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

Pak můžeme kombinovat tyto dva společnosti Oracle, aby je bylo možné otočit mezi oběma stavy a deterministické transformaci $ \ket{+} ^ {\otimes n} $ na $ \ket {0} $ pomocí několika vrstev ch bran, které jsou v poměru k $ \sqrt{2 ^ n} $ (ie $m \propto \sqrt{2 ^ n} $) oproti přibližně $2 ^ n $ vrstvám, které by byly potřeba pro nedeterministické přípravu $ \ket $, a to tak, že se {0} připraví a měří počáteční stav, dokud se nezjistí výsledek $0 $ $.

### <a name="phase-estimation-oracles"></a>Odhad fáze Oracle ###

V případě odhadu fáze jsou Oracle trochu přirozenější.
Cílem ve fázi odhadu je návrh dílčí rutiny, která je schopná vzorkování z eigenvalues matice s jednou jednotkou.
Tato metoda je nepostradatelná v simulaci stavových období, protože pro mnoho fyzických problémů v chemii a materiálové vědy poskytují tyto eigenvalues základní energiesé systémy, které poskytují cenné informace o fázích vytváření materiálů a reakcí v dynamikě pro molekuly.
Každý charakter odhadu fáze vyžaduje vstup s jednou jednotkou.
Tato jednotná část je obvykle popsána jedním ze dvou typů Oracle.

> [!TIP]
> Oba typy Oracle popsané níže jsou uvedené v ukázkách.
> Další informace o průběžných dotazech Oracle najdete v [ukázce **PhaseEstimation** ](https://github.com/microsoft/Quantum/tree/main/samples/characterization/phase-estimation).
> Další informace o samostatných dotazech Oracle najdete v [ukázce **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/phase-estimation).

První typ Oracle, který volá diskrétní dotaz Oracle a představuje uživatelsky definovaný typ <xref:microsoft.quantum.oracles.discreteoracle> , jednoduše zahrnuje jednotnou matici.
Pokud je $U $ jednotkou, jejíž eigenvalues chceme odhadnout, je Oracle pro $U $ jednoduše samostatným předpokladem pro podprogram, který implementuje $U $.
Například jedna může trvat $U $ to je, že pro odhad amplitud se výše definovala $Q Oracle.
Eigenvalues této matice se dá použít k odhadu překrytí mezi počátečními a cílovými stavy, $ \sin ^ 2 (\theta) $, a to za použití kvadratickě méně vzorků, než je třeba v případě, že by to vyžadovalo jinak.
Tím se vyrozumí použití odhadu fáze pomocí Grover Oracle $Q $ jako zadání monikeru odhadu amplitudy.
Další běžnou aplikací, která se běžně používá v rozsahu metrologie, zahrnuje odhad malého úhlu otočení.
Jinými slovy chceme odhadnout $ \theta $ pro neznámou rotující bránu formuláře $R _z (\theta) $.
V takových případech by měla podrutina, s níž komunikujeme, s cílem zjistit tuto pevnou hodnotu $ \theta $ pro bránu je $ $ \begin{align} U & = R_z (\theta) \\ \\ & = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \ théta/2} \end{bmatrix}.
\end{align} $ $

Druhým typem Oracle použitým ve fázi odhad je průběžný dotaz Oracle, reprezentovaný <xref:microsoft.quantum.oracles.continuousoracle> typem.
Průběžný dotaz Oracle pro odhad fáze má formu $U (t) $, kde $t $ je klasický známý reálné číslo.
Pokud máme $U $ být fixní jednotkou, pak má průběžný dotaz Oracle formu $U (t) = U ^ t $.
To nám umožňuje dotazovat se na matice, jako je $ \sqrt{U} $, které se nedaly implementovat přímo v samostatném modelu dotazu.

Tento typ Oracle je užitečný v případě, že nebudete provádět konkrétní jednotnou, ale chcete se dozvědět, jaké jsou vlastnosti generátoru s jednou jednotkou.
Například při simulaci dynamických stavových procesorů je cílem navrhnout okruhy v provozu, které úzce přibližně $U (t) = e ^ {-i H} $ pro matrici Hermitian $H $ a dobu vývoje $t $.
Eigenvalues $U (t) $ přímo souvisí s eigenvalues $H $.
Pokud to chcete vidět, vezměte v úvahu eigenvector $H $: $H \ket{E} = E\ket {E} $. pak se snadno zobrazí z definice Power-Series exponenciálního exponenciálního výrazu, který $U (t) \ket{E} = E ^ {i\phi} \ KET {E} = E ^ {-iEt} \ket{E} $.
Proto se odhaduje eigenphase $U (t) $ poskytne $E eigenvalue $ za předpokladu, že eigenvector $ \ket{E} $ je vstup do algoritmu odhadu fáze.
V tomto případě se ale hodnota $t $ dá zvolit podle uvážení uživatele, protože u jakékoli dostatečně malé hodnoty $t $ se eigenvalue $E $ dá jednoznačně vrátit přes $E =-\ fí/t $.
Vzhledem k tomu, že metody simulace využívání služeb poskytují možnost provádět zlomkové vývoje, jsou tyto algoritmy odhadu fáze při dotazování na určitou dobu další volnou, konkrétně když diskrétní model dotazů umožňuje použít pouze unitaries $U formuláře ^ j $ pro celé číslo $j $. průběžný dotaz Oracle umožňuje přibližnou unitaries ve formě $U ^ t $ pro všechny skutečné hodnoty $t $.
To je důležité pro stlačení každé poslední unce v algoritmech odhadu fází, protože nám umožňuje přesně zvolit experiment, který by poskytoval nejvíc informací o $E $; vzhledem k tomu, že metody založené na diskrétních dotazech musí dělat s kompromisem, a to výběrem nejlepšího celočíselného počtu dotazů v algoritmu.

Jako konkrétní příklad tohoto problému zvažte, jak se při odhadování nejedná o úhel otočení brány, ale frekvence procesu rotujícího systému.
Jednotná, která popisuje takové pole s dobou provozu, je $U (t) = R_z (2 \ Omega t) $ pro dobu vývoje $t $ a neznámá frekvence $ \omega $.
V tomto kontextu můžeme simulovat $U (t) $ pro všechny $t $ pomocí jedné $R _z $ a nemusíte tak omezovat dodržovali jenom na diskrétní dotazy.
Tento souvislý model má také vlastnost, že frekvence větší než $2 \ PI $ se dají poznat z procesů odhadů fází, které používají průběžné dotazy, protože informace o fázi, které by jinak byly maskovány pomocí děleného průřezu funkce, se dají vykrýt z výsledků experimentů provedených na neúměrných hodnotách $t $.
Proto jsou problémy, jako jsou tyto průběžné modely dotazů pro fáze odhadující fáze Oracle, nejen vhodné, ale jsou také vhodnější pro diskrétní model dotazů.
Z tohoto důvodu Q# má funkčnost jak pro formy dotazů, tak pro uživatele, aby se rozhodla o algoritmu odhadu fáze podle svých potřeb a typu Oracle, který je k dispozici.

## <a name="dynamical-generator-modeling"></a>Modely dynamického generátoru ##

Generátory času pro vývoj popisují, jak se stavy vyvíjejí v čase. Například dynamika stavového stavu $ \ket{\psi} $ se řídí rovnicí Schrödinger $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $ s Hermitian maticí $H $, která se označuje jako Hamiltonian, jako generátor pohybu. Byl zadán počáteční stav $ \ket{\psi (0)} $ v čase $t = $0, formální řešení této rovnice v čase $t $ může být v podstatě zapsané $ $ \begin{align} \ket{\psi (t)} = U (t) \ket{\psi (0)}, \end{align} $ $, kde je výraz exponenciální $U (t) = e ^ {-i H} $, označovaný jako jednotkový operátor pro vývoj času. I když se zaměříme na generátory tohoto formuláře v níže uvedeném příkladu, doporučujeme zdůraznit, že koncept se bude považovat za obecnější, například na simulaci otevřených systémů, nebo na více abstraktních rozdílových rovnic.

Hlavním cílem dynamické simulace je implementace operátoru pro vývoj času v některých stavech, který je kódovaný v qubits počítače s procesorem.  V mnoha případech může být Hamiltonian rozdělená na součet některých $d $ jednodušších podmínek.

$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j, \end{align} $ $

v případě, že je v počítači s procesorem na více procesorech snadné implementovat čas v každém termínu. Například pokud $H _j $ je Pauli $X _1X_2 $, který působí na první a druhý prvek registru qubit `qubits` , může být vývoj času v každém čase $t $ implementován jednoduše voláním operace `Exp([PauliX,PauliX], t, qubits[1..2])` , která má signaturu `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` . Jak je popsáno dále v simulaci Hamiltonian, jedno řešení pak bude přibližný vývoj času pomocí $H $ se sekvencí jednodušších operací.

$ $ \begin{align} U (t) & = \left (e ^ {-iH \_ 0 t/r} e ^ {-IH \_ 1 t/r} \cdots e ^ {-IH \_ {d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\ | H \_ j \\ | ^ 2 t ^ 2/r), \end{align} $ $

kde celé číslo $r > $0 řídí chybu aproximace.

Knihovna modelování dynamického generátoru poskytuje rozhraní pro systematické kódování složitých generátorů z pohledu jednodušších generátorů. Tento popis může být předán do, řekněme, že knihovna simulace implementuje časový vývoj pomocí algoritmu simulace výběru, přičemž mnoho podrobností automaticky postará o.

> [!TIP]
> Knihovna dynamického generátoru popsaná níže je uvedena v ukázkách. Příklad založený na modelu Ising naleznete v [ukázce **IsingGenerators** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/generators).
> Příklad založený na molekulovém vodíku najdete v ukázkách [**H2SimulationCmdLine**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line) a [**H2SimulationGUI**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/gui) .

### <a name="complete-description-of-a-generator"></a>Úplný popis generátoru ###

Na nejvyšší úrovni je úplný popis Hamiltonian obsažen v `EvolutionGenerator` uživatelsky definovaném typu, který má dvě součásti.:

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

`GeneratorSystem`Uživatelem definovaný typ je klasický popis Hamiltonian.

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

První prvek `Int` řazené kolekce členů ukládá počet podmínek $d $ v Hamiltonian a druhý prvek `(Int -> GeneratorIndex)` je funkce, která mapuje celočíselný index ve výrazu $ \{ 0, 1,..., d-1 \} $ na `GeneratorIndex` uživatelsky definovaný typ, který jednoznačně identifikuje jednotlivé primitivní podmínky v Hamiltonian. Všimněte si, že vyjádřením shromažďování podmínek v Hamiltonian jako funkce, nikoli jako pole `GeneratorIndex[]` , umožňuje průběžné zpracování, `GeneratorIndex` které je zvlášť užitečné při popisu Hamiltonians s velkým počtem podmínek.

V nerozhodujícím případě nestanovíme konvenci, které primitivní výrazy identifikované pomocí `GeneratorIndex` jsou snadno simulovatelné. Například primitivní výrazy by mohly být Pauli operátory, jak je popsáno výše, ale mohou být také Fermionic Annihilation a operátory vytváření běžně používané v simulaci přístupnosti. Sám o sobě znamená, že `GeneratorIndex` nepopisuje způsob, jakým je čas v době, kdy ukazuje, že je možné implementovat časový okruh.

To je vyřešeno zadáním `EvolutionSet` uživatelsky definovaného typu, který je namapován `GeneratorIndex` z některé kanonické sady na operátor s jednotkou, `EvolutionUnitary` vyjádřený jako okruh. `EvolutionSet`Definuje konvenci `GeneratorIndex` , jak je strukturovaný a také definuje sadu možností `GeneratorIndex` .

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a>Generátory operátorů Pauli ###

Konkrétní a užitečný příklad generátorů jsou Hamiltoniansy, které jsou součtem operátorů Pauli, z nichž každá může s jiným koeficientem.
$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} a_j H_j, \end{align} $ $, kde každá skupina $ \hat H_j $ je nyní vykreslena z Pauli skupiny. Pro tyto systémy poskytujeme `PauliEvolutionSet()` typ `EvolutionSet` , který definuje konvenci pro způsob, jakým může být element Pauli skupiny a koeficientu identifikován `GeneratorIndex` , který má následující signaturu.

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

V našem kódování první parametr `Int[]` Určuje řetězec Pauli, kde $ \Hat I\rightarrow $0, $ \Hat X\rightarrow $1, $ \Hat Y\rightarrow $2 a $ \Hat Z\rightarrow $3. Druhý parametr `Double[]` ukládá koeficient Pauli řetězce v Hamiltonian. Všimněte si, že je použit pouze první prvek tohoto pole. Třetí parametr `Int[]` indexuje qubits, na kterém tento řetězec Pauli funguje, a nesmí mít žádné duplicitní prvky. Proto Hamiltonian Term $0,4 \hat X_0 \hat Y_8 \hat I_2 \hat Z_1 $ může být reprezentován jako

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

`PauliEvolutionSet()`Je funkce, která mapuje libovolný `GeneratorIndex` z tohoto formuláře na `EvolutionUnitary` s následující signaturou.

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

První parametr představuje časový interval, který bude vynásoben koeficientem v rámci `GeneratorIndex` jednotkového vývoje. Druhým parametrem je qubit, na kterém se registruje jednotná činnost. 

### <a name="time-dependent-generators"></a>Generátory závislé na čase ###

V mnoha případech jsme se také zajímat o generátory závislé na čase modelování, ke kterým může dojít v Schrödinger rovnici $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = \hat H (t) \ket{\psi (t)}, \end{align} $ $, kde generátor $ \hat H (t) $ je teď závislý na čase. Rozšíření od zdrojů nezávislých na čase výše tohoto případu je jednoduché. Místo toho, abyste měli pevně `GeneratorSystem` popisující Hamiltonian pro všechny časy $t $, máme k tomu `GeneratorSystemTimeDependent` uživatelsky definovaný typ.

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

První parametr je parametr průběžného plánu $s \in [0, 1] $ a funkce tohoto typu vrátí `GeneratorSystem` pro tento plán. Všimněte si, že parametr Schedule může být lineární v souvislosti s parametrem fyzického času, například $s = t/T $, pro určitý celkový čas simulace $T $. Obecně to ale nemusí být případ.

Podobně úplný popis tohoto generátoru vyžaduje `EvolutionSet` , a proto definujeme `EvolutionSchedule` uživatelsky definovaný typ.

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
