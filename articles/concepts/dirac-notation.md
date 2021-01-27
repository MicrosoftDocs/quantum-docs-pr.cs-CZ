---
title: Dirac Notation Description: Naučte se používat zápis Dirac pro reprezentaci stavových a simulací operací.
Autor: QuantumWriter UID: Microsoft.. koncepty. Dirac MS. Author: v-benbra MS. Date: 12/11/2017 MS. téma: koncepční No-Loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="dirac-notation"></a>Zápis Dirac

V případě, že je všudypřítomný vektorového zápisu v lineárním algebraický, je často náročný na výpočetní výkon, zejména při práci s více qubits.  Například pokud definujeme jako $ \psi $ vektor, není explicitně jasné, zda $ \psi $ se jedná o vektor řádku nebo sloupce.  Proto pokud $ \phi $ a $ \psi $ jsou vektory, je stejně nejasné, pokud $ \phi \psi $ je dokonce definována, protože prvky $ \phi $ a $ \psi $ mohou být v kontextu nejasné.  Nad rámec nejednoznačnosti na tvarech vektorů a vyjadřující ještě jednoduché vektory pomocí lineárního algebraických Notation, který jste dříve zavedli, může být velmi obtížné. Pokud si například přejete popsat $ n $ -qubit stav, kde každé qubit převezme hodnotu 0, $ tak $ by byl stav popsán jako 

$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} 1 \\\\ \end{bmatrix} . $$  

Kurz vyhodnocování tohoto tensor produktu je nepraktický, protože vektor leží v exponenciálním velkém prostoru, takže tento zápis je ve skutečnosti nejlepším popisem stavu, který může být dán pomocí předchozího zápisu.  

[*Dirac Notation*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) řeší tyto problémy tím, že prezentuje nový jazyk, který bude vyhovovat přesným potřebám mechanismu plnění.  Z tohoto důvodu doporučujeme, aby čtenář nezobrazil příklady v této části jako tuhý předpis o tom, jak tyto stavy popsat, ale místo toho je povzbuzovat, aby si ho mohli zobrazit jako návrhy, které se dají použít k stručné vyjádření nápadů.

Existují dva typy vektorů v Dirac Notation: *Bra* Vector a *KET* Vector, takže při jejich sečtení tvoří *brzdový* nebo vnitřní produkt.  Pokud $ \psi $ je vektorem sloupce, můžeme ho zapsat do zápisu Dirac jako $ \ket { \psi } $ , kde $ \ket { \cdot } $ označuje, že se jedná o vektor sloupce jednotek, tj. *KET* Vector.  Podobně se vektor řádku $ \psi ^ \dagger $ vyjadřuje jako $ \bra { \psi } $ . Jinými slovy, $ \psi ^ \dagger $ je získáno pomocí komplexního conjugation položky, které jsou k dispozici pro prvky transpozice $ \psi $ . Zápis Bra-KET přímo naznačuje, že $ \braket { \psi | \psi } $ se jedná o vnitřní součin vektoru $ \psi $ se sebou samým, což je definice $ 1 $ .  

Obecně platí, $ \psi $ že pokud a $ \phi $ jsou vektory stavu, jejich vnitřní produkt je $ \braket { \phi | \psi } $ , což znamená, že pravděpodobnost měření stavu $ \ket { \psi } $ $ \ket { \phi } $ je $ | \braket { \phi | \psi } | ^ 2 $ .  

Následující konvence se používá k popsání stavových procesorů, které zakódují hodnoty nula a One (qubit výpočetních základních stavů):

$$
\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket { 0 } ,\qquad
\begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \ket { } .
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>Příklad: reprezentace operace Hadamard se zápisem Dirac

Následující notace se často používá k popisu stavů, které vyplývají z použití brány Hadamard na $ \ket { hodnotu 0 } $ a $ \ket { 1 } $ (které odpovídají vektorům jednotky v $ směrech + x $ a $ -x $ v koule Bloch):

$$
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ \end{bmatrix} = H \ket { 0 } = \ket { + } ,\qquad
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ – 1 \end{bmatrix} = H \ket { 1 } = \ket { - } .
$$

Tyto stavy je také možné rozšířit pomocí Dirac Notation jako součty $ \ket { 0 } $ a $ \ket { 1 } $ :

$$
\ket{+}= \frac{ 1 } { \sqrt { 2 } } ( \ket { 0 }  +  \ket { 1 } ), \qquad \ket { - } = \frac { 1 } { \sqrt { 2 } } ( \ket { 0 }  -  \ket { 1 } ).
$$

### <a name="computational-basis-vectors"></a>Vektory výpočetního základu

To ukazuje, proč se tyto stavy často označují jako *výpočetní základ*: každý stav bez teček může být vždy vyjádřen jako součet výpočetních vektorů a tyto součty se snadno vyjadřují pomocí Dirac Notation.  Tato konverzace je také pravdivá v tom, že stavy $ \ket { + } $ a $ \ket { - } $ také tvoří základ pro stavové stavy.  Můžete to vidět z faktu, že

$$
\ket{0 } = \frac { 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ), \qquad \ket { 1 } = \frac { 1 } { \sqrt { 2 } } ( \ket { + }  -  \ket { - } ).
$$

Jako příklad zápisu Dirac zvažte brzdu $ \braket { 0 | 1 } $ , což je vnitřní produkt mezi $ 0 $ a $ 1 $ .  Dá se zapsat jako 

$$
\braket{0 | 1 } = \begin{bmatrix} & 0 0 \end{bmatrix} \begin{bmatrix} \\\\ 1 0 \end{bmatrix} = .
$$

To říká, že $ \ket { 0 } $ a $ \ket { 1 } $ jsou kolmé vektory, což znamená, že $ \braket { 0 | 1 } = \braket { | 0 } = 0 $ .  Také definicí $ \braket { 0 | 0 1 1 } = \braket { | } = $ , což znamená, že dva vektory výpočetního základu mohou být také volány *orthonormal*.

Tyto vlastnosti orthonormal budou užitečné v následujícím příkladu. Pokud máme stav $ \ket { \psi } = { \frac { 3 } { 5 } } \ket { 1 }  +  { \frac { 4 } { 5 } } \ket { 0 } $ $ \braket { , potom 1 | 0 } = 0 $ , pravděpodobnost měření $ 1 $ je 

$$
\big|\braket{1 | \psi } \big | ^ 2 = \left | \frac { 3 } { 5 } \braket { 1 | 1 }  + \frac { 4 } { 5 } \braket { 1 | 0 } \right | ^ 2 = \frac { 9 } { 25 } .
$$

### <a name="tensor-product-notation"></a>Zápis produktu tensor

Zápis Dirac zahrnuje také implicitní strukturu produktů tensor v rámci něj.  To je důležité z toho důvodu, že v případě, že se jedná o výpočetní výkon, je vektor stavu, který popisuje dva nekorelační Registry, tensor produkty dvou vektorů stavu.  Stručně popisující strukturu produktu tensor nebo její nedostatečného je důležité, pokud chcete vysvětlit výpočet.  Struktura produktu tensor předpokládá, že můžeme napsat $ \psi \otimes \phi $ pro jakékoli dva vektory stavových prostředí $ \phi $ a $ \psi $ jako $ \ket { \psi } \ket { \phi } $ , někdy explicitně zapsané jako $ \ket { \psi } \otimes \ket { \phi } $ , ale v konvenci psaní $ \otimes $ v mezi vektory nejsou zbytečné.  Například stav se dvěma qubits inicializovanými do nulového stavu je dán

$$
\begin{bmatrix}1 0 0 0 0 0 0 0 \\\\ \\\\ \\\\ \end{bmatrix} = \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} = \ket { } \otimes \ket { } = \ket { } \ket { } . 1 0
$$

Podobně stav $ \ket { p } $ pro celé číslo $ p $ představuje stav bez hodnoty, který kóduje v binárním vyjádření celé číslo $ p $ .  Pokud si například přejete vyjádřit číslo $ 5 $ pomocí binárního kódování bez znaménka, můžeme ho stejně vyjádřit jako

$$
\ket{1 } \ket { 0 } \ket { 1 } = \ket { 101 } = \ket { 5 } .
$$

V tomto zápisu $ \ket { 0 } $ nemusí odkazovat na qubit stav, ale místo *registrace qubit* ukládání binárního kódování $ 0 $ .  Rozdíly mezi těmito dvěma zápisy jsou obvykle jasně jasné z kontextu.  Tato konvence je užitečná pro zjednodušení prvního příkladu, který lze zapsat některým z následujících způsobů:

$$
\begin{bmatrix}1 0 0 0 0 0 0 \\\\ \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} \\\\ \end{bmatrix} = \ket { } \otimes \cdots \otimes \ket { } = | \cdots \rangle = \ket { n 0 } ^ { \otimes } = \ket { } .
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>Příklad: popisující pozici Dirac Notation

Jako další příklad, jak můžete použít Dirac Notation k popsání státu, zvažte následující ekvivalenty při psaní stavových stavů, který je stejně větší než u každého možného bitového řetězce délky $ n.$

$$
H ^ { \otimes n } \ket { 0 } = \frac { 1 } { 2 ^ { n/2 } } \sum _ { j = 0 } ^ { 2 ^ n-1 } \ket { j } = \ket { + } ^ { \otimes n } .
$$

V této části se můžete setkat s tím, proč součet přechází z $ 0 $ na $ 2 ^ { n } -1 $ pro $ n $ bitů.  Nejdřív si všimněte, že je $ 2 ^ { n } $ různých konfigurací, které $ n $ bitů může trvat.  Můžete se podívat, že jeden bit může mít $ 2 hodnoty, $ ale dvě bity můžou mít $ 4 $ hodnoty a tak dále. Obecně to znamená, že existuje $ 2 ^ n $ různých možných bitových řetězců, ale největší hodnota zakódovaná v jednom z nich $ 1 \cdots 1 = 2 ^ n-1 $ , a proto je horním limitem pro součet.
Jako Poznámka na straně, v tomto příkladu jsme nepoužívali $ \ket { + } ^ { \otimes n } = \ket { + } $ v analogii na $ \ket { 0 } ^ { \otimes n } = \ket { 0, } $ protože tato konvence zápisu je obvykle vyhrazena pro výpočetní stav na základě každého qubit inicializovaného na nulu.  I když by taková konvence rozumné v tomto případě, nejedná se o výpočetní prostředí.

### <a name="expressing-linearity-with-dirac-notation"></a>Vyjádření linearity pomocí notace Dirac

Další dobrým prvkem Dirac Notation je skutečnost, že je lineární.  Pokud chceme napsat pro všechny čtyři stavy stavu, 

$$( \alpha \ket { \psi }  + \beta \ket { \phi } ) \otimes ( \gamma \ket { \chi }  +  \delta \ket { \omega } ) = \alpha \gamma \ket { \psi } \ket { \chi }  +  \alpha \delta \ket { \psi } \ket { \omega } + \beta \gamma \ket { \phi } \ket { \chi } + \beta \delta \ket { \phi } \ket { \omega } .$$

To znamená, že je možné distribuovat zápis produktu tensor v zápisu Dirac, takže přebírání tensor produktů mezi vektory stavu končí hledáním stejně jako v případě obyčejného násobení.

Vektory Bra sledují podobnou konvenci pro KET vektory.  Například vektor $ \bra { \psi } \bra { \phi } $ je ekvivalentem stavu Vector $ \psi ^ \dagger \otimes \phi ^ \dagger = ( \psi \otimes \phi ) ^ \dagger $ . Pokud je vektor KET $ \ket { \psi } $ $ \alpha \ket { 0 }  +  \beta \ket { 1 } $ , verze vektoru Bra vektoru je $ \bra { \psi } = \ket { \psi } ^ \dagger = ( \bra { 0 } \alpha ^ * + \bra { 1 } \beta ^ *) $ .

Představte si například, že chceme vypočítat pravděpodobnost měření stavu $ \ket { \psi } = \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 } { 5 } \ket { 0 } $ pomocí programu pro měření stavů, které mají být buď $ \ket { + } $ nebo $ \ket { - } $ . Pak pravděpodobnost, že bude zařízení výstupem stavu $ \ket { - } $ 

$$|\braket{- |\psi}| ^ 2 = \left | \frac { 1 } { \sqrt { 2 } } ( \bra { 0 }  -  \bra { 1 } ) ( \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 } { 5 } \ket { 0 } ) \right | ^ 2 = \left | - \frac { 3 } { 5 \sqrt { 2 } }  +  \frac { 4 } { 5 \sqrt { 2 } } \right | ^ 2 = \frac { 1 } { 50 } .$$

Skutečnost, že se záporné znaménko objeví při výpočtu pravděpodobnosti, je manifestem rušivého rušení, což je jeden z mechanismů, kterými výpočetní výkon získá výhody oproti klasickému výpočetnímu prostředí.

## <a name="ketbra-or-outer-product"></a>ketbra nebo vnější produkt

Konečná položka, která je předmětem diskuze v Dirac Notation, je *ketbra* nebo vnější produkt.  Vnější produkt je reprezentován v Dirac zápisech jako $ \ket { \psi } \bra { \phi } $ a někdy označovaný jako ketbras, protože Bras a kets se vyskytují v opačném pořadí jako brakets.  Vnější produkt je definován pomocí násobení matic, jako u násobcích $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger $ stavových vektorů $ \psi $ a $ \phi $ .  Nejjednodušším a pravděpodobně Nejběžnějším příkladem tohoto zápisu je

$$
\ket{0 } \bra { 0 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \begin{bmatrix} & \end{bmatrix} = \begin{bmatrix} & \\\\ & \end{bmatrix} \qquad \ket { } \bra { } = \begin{bmatrix} \\\\ \end{bmatrix} \begin{bmatrix} & \end{bmatrix} = \begin{bmatrix} & \\\\ & \end{bmatrix} 1 0 0 0 0 0 0 1 0 0 0 0 0
$$

Ketbras se často nazývají projektory, protože projektují stav na pevnou hodnotu.  Vzhledem k tomu, že tyto operace nejsou jednotkové (a dokonce i zachovat normu vektoru), mělo by být neuvedeno, že počítač s více operačními počítači nemůže deterministickém způsobem použít projektor.  Projektory se dotýkají působivé úlohy popisující akci, kterou měření má v nestavovém stavu.  Například pokud měříme stav $ \ket { \psi } $ na $ 0 $ , pak výsledná transformace, která má stav v důsledku měření, je

  $$\ket{\psi}\right \frac šipka { ( \ket { 0 } \bra { 0 } ) \ket { \psi } } { | \braket { 0 | \psi } | } = \ket { 0 } ;$$

očekává se, že pokud byste chtěli změřit stav a najít ho jako $ \ket { 0 } $ .  Chcete-li provést iteraci, nelze tyto projektory použít ve stavu v počítači s více než jednou.  Místo toho je lze použít náhodně s výsledkem $ \ket { 0 s } $ určitou pevnou pravděpodobností.  Pravděpodobnost takového měření se může zapsat jako hodnota očekávaného projektoru ve stavu.

$$
\bra{\psi}( \ket { 0 } \bra { 0 } ) \ket { \psi } = | \braket { \psi | 0 } | ^ 2,$$

To ukazuje, že projektory jednoduše poskytují nový způsob, jak vyjádřit proces měření.

Pokud místo toho považujeme za první qubit stavu qubit na hodnotu $ 1, $ můžeme také tento proces snadno popsat pomocí projektorů a Dirac zápisu:

$$
P ( \text { první qubit = 1 } ) = \bra { \psi } \left ( \ket { 1 } \bra { 1 } \otimes \boldone ^ { \otimes n-1 } \right ) \ket { \psi } .
$$

Tady se může v zápisu Dirac pohodlně napsat matice identity jako

$$
\boldone= \ket{ 0 } \bra { 0 } + \ket { 1 1 } \bra { } = \begin{bmatrix} & 0 \\\\ & \end{bmatrix} 0 1.
$$

V případě, že je možné qubits projektor rozšířit na dva, jako 

$$
\ket{1 1 1 } \bra { } \otimes \id = \ket { } \bra { } \otimes ( \ket { 0 } \bra { 0 } + \ket { 1 1 } \bra { } ) = \ket { 10 } \bra { 10 }  +  \ket { 11 } \bra { 11 } .
$$

Uvidíte, že je to v souladu s diskusí o pravděpodobnosti měření pro stavy multiqubit pomocí notace sloupcový-Vector:

$$
P ( \text { první qubit = 1 } ) = \psi ^ \dagger (e \_ { 10 } e \_ { 10 } ^ \dagger + e \_ { 11 } e \_ { 11 } ^ \dagger ) \psi = | e \_ { 10 } ^ \dagger \psi | ^ 2 + | e \_ { 11 } ^ \dagger \psi | ^ 2,$$

který se shoduje s qubitou diskuzi o měření.  Vygeneralizení tohoto výsledku pro qubit případ je však poněkud jednodušší, aby bylo možné vyjádřit pomocí notace Dirac, než je zápis ve sloupcovém vektoru, a je zcela ekvivalentní k předchozímu ošetření.

## <a name="density-operators"></a>Operátory hustoty

Dalším užitečným operátorem k vyjádření použití notace Dirac je *operátor hustoty*, někdy také označovaný jako *operátor State*.
Operátor hustoty pro vektorový stavový vektor má formu $ \rho = \ket { \psi } \bra { \psi } $ .
Tento koncept představující stav jako matici, spíše než vektor, je často pohodlný, protože poskytuje pohodlný způsob, jak vyjádřit výpočty pravděpodobnosti a také umožňuje, aby popsal statistickou nejistotu i nejistotu v rámci stejné formality.
Obecné operátory státních stavů, nikoli vektory, se všudypřítomný v některých oblastech výpočetního prostředí, ale není nutné porozumět základům tohoto pole.
Pro zúčastněný čtenář doporučujeme přečíst si jednu z referenčních knih, které jsou k dispozici v tématu, [kde najdete další informace](xref:microsoft.quantum.more-information).

## <a name="no-locq-gate-sequences-equivalent-to-quantum-states"></a>Q# sekvence brány rovnající se státům

Konečný bod pro vyzvednutí zápisu do teček a Q# programovací jazyk: na začátku tohoto dokumentu jsme uvedli, že stav nekonečných stavů je základní objekt informací ve výpočetním prostředí.  Pak může nastat jako neočekávaně, že v Q# žádném případě neexistují žádné fiktivní stavy.  Místo toho jsou všechny stavy popsány pouze pomocí operací, které slouží k jejich přípravě.  Předchozí příklad představuje vynikající ilustraci.  Místo toho, abychom v registru vyjádřili jednotnou pozici pro všechny bitové řetězce, můžeme výsledek vyjádřit jako $ H ^ { \otimes n } \ket { 0 } $ .  Tento exponenciálně kratší popis stavu má nejen výhodu, že se na něj dá klasický důvod, ale také stručně definuje operace, které je potřeba rozšířit prostřednictvím softwarového zásobníku, aby se tento algoritmus implementoval.  Z tohoto důvodu Q# je navržena tak, aby vygenerovala sekvence brány místo nestavových stavů. na teoretické úrovni jsou však dva perspektivy stejné.
