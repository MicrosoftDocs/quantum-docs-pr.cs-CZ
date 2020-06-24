---
title: Diracova notace
description: Přečtěte si, jak používat zápis Dirac, který představuje stavy a simuluje operace.
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: f9dddfa25e9fd1e3d8aaf92b2e3b17c96ed8b72a
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269502"
---
# <a name="dirac-notation"></a>Zápis Dirac

V případě, že je všudypřítomný vektorového zápisu v lineárním algebraický, je často náročný na výpočetní výkon, zejména při práci s více qubits.  Například pokud definujeme $ \psi jako $ vektor, není explicitně jasné, zda je $ \psi $ řádek nebo vektor sloupce.  Proto pokud jsou $ \phi $ a $ \psi $ vektory, je stejně nejasné, pokud je $ \phi \psi $ dokonce definovaný, protože tvary $ \phi $ a $ \psi $ mohou být v kontextu nejasné.  Nad rámec nejednoznačnosti na tvarech vektorů a vyjadřující ještě jednoduché vektory pomocí lineárního algebraických Notation, který jste dříve zavedli, může být velmi obtížné. Pokud si například přejete popsat $n $ qubit, kde každé qubit převezme hodnotu $0, tak $ by byl tento stav formálně vyjadřovat jako 

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cdots \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } . $$  

Kurz vyhodnocování tohoto tensor produktu je nepraktický, protože vektor leží v exponenciálním velkém prostoru, takže tento zápis je ve skutečnosti nejlepším popisem stavu, který může být dán pomocí předchozího zápisu.  

[*Dirac Notation*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) řeší tyto problémy tím, že prezentuje nový jazyk, který bude vyhovovat přesným potřebám mechanismu plnění.  Z tohoto důvodu doporučujeme, aby čtenář nezobrazil příklady v této části jako tuhý předpis o tom, jak tyto stavy popsat, ale místo toho je povzbuzovat, aby si ho mohli zobrazit jako návrhy, které se dají použít k stručné vyjádření nápadů.

Existují dva typy vektorů v Dirac Notation: *Bra* Vector a *KET* Vector, takže při jejich sečtení tvoří *brzdový* nebo vnitřní produkt.  Pokud $ \psi $ je vektorem sloupce, můžeme ho zapsat do Dirac Notation jako $ \ket { \psi } $, kde $ \ket { \cdot } $ označuje, že se jedná o vektor sloupce jednotek, tj. *KET* Vector.  Podobně je řádek Vector $ \psi ^ \dagger $ vyjádřen jako $ \bra { \psi } $. Jinými slovy, $ \psi ^ \dagger $ se získá tím, že se k prvkům transponovat z $ \psi aplikují komplexní conjugation $ . Zápis Bra-KET přímo naznačuje, že $ \braket { \psi | \psi } $ je vnitřní produkt vektor $ \psi $ se sebou samým, což je definice $1 $ .  

Obecně platí, že pokud jsou $ \psi $ a $ \phi, $ jejich vnitřní součin je $ \braket { \phi | \psi } $, což znamená, že pravděpodobnost měření stavu $ \ket \psi { } $ na $ \ket \phi $ { } je $ | \braket { \phi | \psi } | ^ 2 $ .  

Následující konvence se používá k popsání stavových procesorů, které zakódují hodnoty nula a One (qubit výpočetních základních stavů):

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } , \qquad \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } = \ket{1 } .
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>Příklad: reprezentace operace Hadamard se zápisem Dirac

Následující notace se často používá k popisu stavů, které vznikají v důsledku použití brány Hadamard na $ \ket{0 } $ a $ \ket{1 } $ (které odpovídají vektorům jednotek v $ přísměrech $ + x a $-x $ v koule Bloch):

$ $ \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ 1 \end{ bmatrix } = H \ket {0 } = \ket { +}, \qquad \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ -1 \end{ bmatrix } = H \ket {1 } = \ket { -}.
$$

Tyto stavy je také možné rozšířit pomocí Dirac Notation jako součty pro $ \ket{0 } $ a $ \ket{1 } $:

$ $ \ket { +} = \frac{1 } {\sqrt{2 } } (\ket{0 } + \ket{1 } ), \qquad \ket { -} = \frac{1 } {\sqrt{2 } } (\ket{0 } -\ket{1 } ).
$$

### <a name="computational-basis-vectors"></a>Vektory výpočetního základu
To ukazuje, proč se tyto stavy často označují jako *výpočetní základ*: každý stav bez teček může být vždy vyjádřen jako součet výpočetních vektorů a tyto součty se snadno vyjadřují pomocí Dirac Notation.  Tato konverzace je také pravdivá v tom, že stavy $ \ket { +} $ a $ \ket { -} $ také tvoří základ pro stavové stavy.  Můžete to vidět z faktu, že

$ $ \ket{0 } = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}), \qquad \ket{1 } = \frac{1 } {\sqrt{2 } } (\ket { +}-\ket { -}).
$$

Jako příklad zápisu Diracu Zvažte možnost brzdit $ \braket{0 | 1 } $, což je vnitřní produkt mezi $0 $ a $1 $ .  Dá se zapsat jako 

$ $ \braket{0 | 1 } = \begin{ bmatrix } 1 & 0 \end{ bmatrix } \begin{ bmatrix } 0 \\\\ 1 \end{bmatrix} = 0. $ $

Říká se tomu, že $ \ket{0 } $ a $ \ket{1 } $ jsou kolmé vektory, což znamená $ \braket{0 | 1 } = \braket{1 | 0 } = 0 $ .  Také podle definice $ \braket{0 | 0 } = \braket{1 | 1 } = 1 $ , což znamená, že dva vektory výpočetního základu mohou být také volány *orthonormal*.
Tyto vlastnosti orthonormal budou užitečné v následujícím příkladu. Pokud máme stav $ \ket { \psi } = {\frac{3 } {5 } } \ket{1 } + {\frac{4 } {5 } } \ket{0 } $ then, protože $ \braket{1 | 0 } = 0 $ pravděpodobnost měření $1 $ je  

$ $ \big | \braket{1 | \psi } \big | ^ 2 = \left | \frac{3 } {5 } \braket{1 | 1 } + \frac{4 } {5 } \braket{1 | 0 } \right | ^ 2 = \frac{9 } {25 } . $ $ 

### <a name="tensor-product-notation"></a>Zápis produktu tensor
Zápis Dirac zahrnuje také implicitní strukturu produktů tensor v rámci něj.  To je důležité z toho důvodu, že v případě, že se jedná o výpočetní výkon, je vektor stavu, který popisuje dva nekorelační Registry, tensor produkty dvou vektorů stavu.  Stručně popisující strukturu produktu tensor nebo její nedostatečného je důležité, pokud chcete vysvětlit výpočet.  Struktura produktu tensor předpokládá, že můžeme napsat $ \psi \otimes \phi $ pro jakékoli dvě "vektory stavu" \phi $ a $ \psi $ jako $ \ket { \psi } \ket { \phi } $, někdy explicitně zapsané jako $ \ket { \psi } \otimes \ket { \phi } $, ale konvence psaní $ \otimes $ v mezi vektory není zbytečné.  Například stav se dvěma qubits inicializovanými do nulového stavu je dán

$ $ \begin{ bmatrix } 1 \\ \\ 0 0 \\ \\ \\ \\ 0 \end{ bmatrix } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } \otimes \ket{0 } = \ket{0 } \ket{0 } .
$$

Podobně stav $ \ket{p } $ pro celočíselný $p $ představuje stav bez hodnoty, který se zakóduje v binární reprezentaci na celé číslo $p $ .  Například pokud chceme vyjádřit číslo $5 $ pomocí binárního kódování bez znaménka, můžeme ho stejně vyjádřit jako

$ $ \ket{1 } \ket{0 } \ket{1 } = \ket{101 } = \ket{5 } .
$$

V tomto zápisu $ \ket{0 } $ nemusí odkazovat na stav s jedním qubit, ale místo *registrace qubit* uložit binární kódování $0 $ .  Rozdíly mezi těmito dvěma zápisy jsou obvykle jasně jasné z kontextu.  Tato konvence je užitečná pro zjednodušení prvního příkladu, který lze zapsat některým z následujících způsobů:

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cdots \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } \otimes \cdots \otimes \ket{0 } = | 0 \cdots 0 \rangle = \ket{0 } ^ {\otimes n } = \ket{0 } .
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>Příklad: popisující pozici Dirac Notation
Dalším příkladem, jak můžete použít Dirac Notation k popsání státu, zvažte následující ekvivalenty při psaní stavových stavů, které jsou stejné jako u každého možného bitového řetězce délky $n$

$ $ H ^ {\otimes n } \ket{0 } = \frac{1 } {2 ^ {n/2 } } \ sum_ {j = 0 } ^ {2 ^ n-1 } \ket{j } = \ket { +} ^ {\otimes n } .
$$

V této části se můžete zajímat, proč součet z $0 $ do $2 ^ {n } -1 $ pro $n $ bitů.  Nejdřív si všimněte, že je k dispozici $2 ^ {n } $ různých konfigurací, které $n $ BITS může trvat.  Můžete se podívat, že jeden bit může přijmout $2 hodnot, $ ale dvě bity mohou přijmout $4 $ hodnoty a tak dále. Obecně to znamená, že existuje $2 ^ n $ různých možných bitových řetězců, ale největší hodnota je kódována v jednom z nich $1 \cdots 1 = 2 ^ n-1 $ , a proto je horním limitem pro součet.
Jako poznámku na straně, v tomto příkladu jsme nepoužili $ \ket { +} ^ {\otimes n } = \ket { +} $ v analogii na $ \ket{0 } ^ {\otimes n } = \ket{0 } $, protože tato konvence zápisu je obvykle vyhrazená pro výpočetní stav se všemi qubity inicializovanými na nulu.  I když by taková konvence rozumné v tomto případě, nejedná se o výpočetní prostředí.

### <a name="expressing-linearity-with-dirac-notation"></a>Vyjádření linearity pomocí notace Dirac
Další dobrým prvkem Dirac Notation je skutečnost, že je lineární.  Pokud chceme napsat pro všechny čtyři stavy stavu, 

$ $ (\Alpha \ket { \psi } + \beta \ket { \phi } ) \otimes (\gamma \ket { \chi } + \delta \ket { \omega } ) = \Alpha \gamma \ket { \psi } \ket { \chi } + \Alpha \delta \ket { \psi } \ket { \omega } + \beta \gamma \ket { \phi } \ket { \chi } + \beta \delta \ket { \phi } \ket { \omega } . $ $

To znamená, že je možné distribuovat zápis produktu tensor v zápisu Dirac, takže přebírání tensor produktů mezi vektory stavu končí hledáním stejně jako v případě obyčejného násobení.

Vektory Bra sledují podobnou konvenci pro KET vektory.  Například Vector $ \bra { \psi } \bra { \phi } $ je ekvivalentem State Vector $ \psi ^ \dagger \otimes \phi ^ \dagger = (\psi \otimes \phi) ^ \dagger $ . Pokud je KET Vector $ \ket { \psi } $ $ \Alpha \ket{0 } + \beta \ket{1 } $, pak je verze vektoru Bra \bra $ \psi { \ket } = \psi { \dagger } ^ \bra{0 = (\Alpha } \bra{1 ^ * + \beta } ^ *) $.

Představte si například, že chceme vypočítat pravděpodobnost měření stavu $ \ket { \psi } = \frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } $ pomocí programu pro měření stavů na hodnotu $ \ket { +} $ nebo $ \ket { -} $. Pak pravděpodobnost, že by zařízení mělo výstup do stavu $ \ket { -} $ 

$ $ | \braket { -| \psi } | ^ 2 = \left | \frac{1 } {\sqrt{2 } } (\bra{0 } -\bra{1 } ) (\frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } ) \right | ^ 2 = \left | -\frac{3 } {5 \sqrt {2 } } + \frac{4 } {5 \sqrt {2 } } \right | ^ 2 = \frac{1 } {50 } . $ $

Skutečnost, že se záporné znaménko objeví při výpočtu pravděpodobnosti, je manifestem rušivého rušení, což je jeden z mechanismů, kterými výpočetní výkon získá výhody oproti klasickému výpočetnímu prostředí.

## <a name="ketbra-or-outer-product"></a>ketbra nebo vnější produkt
Konečná položka, která je předmětem diskuze v Dirac Notation, je *ketbra* nebo vnější produkt.  Vnější produkt je reprezentován v Dirac zápisy jako $ \ket { \psi } \bra { \phi } $ a někdy se označuje jako ketbras, protože Bras a kets se vyskytují v opačném pořadí jako brakets.  Vnější produkt je definován pomocí násobení matic jako $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger pro násobky $ stavových vektorů $ \psi $ a $ \phi $ .  Nejjednodušším a pravděpodobně Nejběžnějším příkladem tohoto zápisu je

$ $ \ket{0 } \bra{0 } = \begin{ bmatrix } 1 \\\\ 0 \end{ bmatrix } \begin{ bmatrix } 1&0 \end{ bmatrix } = \begin{ bmatrix } 1 &0 \\\\ 0 &0 \end{bmatrix} \qquad \ket{1 } \bra{1 } = \begin{ bmatrix } 0 \\\\ 1 \end{ bmatrix } \begin{ bmatrix } 0&1 \end{ bmatrix } = \begin{ bmatrix } 0 &0 \\\\ 0 &1 \end{bmatrix} .
$$

Ketbras se často nazývají projektory, protože projektují stav na pevnou hodnotu.  Vzhledem k tomu, že tyto operace nejsou jednotkové (a dokonce i zachovat normu vektoru), mělo by být neuvedeno, že počítač s více operačními počítači nemůže deterministickém způsobem použít projektor.  Projektory se dotýkají působivé úlohy popisující akci, kterou měření má v nestavovém stavu.  Pokud například měříme stav $ \ket { \psi } $, který bude $0 $ , pak výsledná transformace, která se v důsledku měření funguje jako stav, je

  $ $ \ket { \psi } \rightarrow \frac { (\ket{0 } \bra{0 } ) \ket { \psi } } {| \braket{0 | \psi } |} = \ket{0 } , $ $

očekává se, že pokud byste chtěli změřit stav a vyhledat ho jako $ \ket{0 } $.  Chcete-li provést iteraci, nelze tyto projektory použít ve stavu v počítači s více než jednou.  Místo toho je lze použít náhodně s výsledným $ \ket{0 } $ zobrazeným s určitou pevnou pravděpodobností.  Pravděpodobnost takového měření se může zapsat jako hodnota očekávaného projektoru ve stavu.

$ $ \bra { \psi } (\ket{0 } \bra{0 } ) \ket { \psi } = | \braket { \psi | 0 } | ^ 2, $ $

To ukazuje, že projektory jednoduše poskytují nový způsob, jak vyjádřit proces měření.

Pokud místo toho zvažte měření prvního qubit stavu qubit na hodnotu $1, $ můžeme také tento proces snadno popsat pomocí projektorů a notace Dirac:

$ $ P (\Text{First qubit = 1 } ) = \bra { \psi } \left (\ket{1 } \bra{1 } \otimes \boldone ^ {\otimes n-1 } \right) \ket { \psi } .
$$

Tady se může v zápisu Dirac pohodlně napsat matice identity jako

$ $ \boldone = \ket{0 } \bra{0 } + \ket{1 } \bra{1 } = \begin{ bmatrix } 1&0 \\\\ 0&1 \end{ bmatrix } .
$$

V případě, že je možné qubits projektor rozšířit na dva, jako 

$ $ \ket{1 } \bra{1 } \otimes \id = \ket{1 } \bra{1 } \otimes (\ket{0 } \bra{0 } + \ket{1 } \bra{1 } ) = \ket{10 } \bra{10 } + \ket{11 } \bra{11 } .
$$

Uvidíte, že je to v souladu s diskusí o pravděpodobnosti měření pro stavy multiqubit pomocí notace sloupcový-Vector:

$ $ P (\Text{First qubit = 1 } ) = \psi ^ \dagger (e \_ {10} e \_ {10 } ^ \dagger + e \_ {11} e \_ {11 } ^ \dagger) \psi = | e \_ {10 } ^ \dagger \psi | ^ 2 + | e \_ {11 } ^ \dagger \psi | ^ 2, $ $

který se shoduje s qubitou diskuzi o měření.  Vygeneralizení tohoto výsledku pro qubit případ je však poněkud jednodušší, aby bylo možné vyjádřit pomocí notace Dirac, než je zápis ve sloupcovém vektoru, a je zcela ekvivalentní k předchozímu ošetření.

## <a name="density-operators"></a>Operátory hustoty

Dalším užitečným operátorem k vyjádření použití notace Dirac je *operátor hustoty*, někdy také označovaný jako *operátor State*.
Operátor hustoty pro vektorový stavový vektor má formu $ \rho = \ket { \psi } \bra { \psi } $.
Tento koncept představující stav jako matici, spíše než vektor, je často pohodlný, protože poskytuje pohodlný způsob, jak vyjádřit výpočty pravděpodobnosti a také umožňuje, aby popsal statistickou nejistotu i nejistotu v rámci stejné formality.
Obecné operátory státních stavů, nikoli vektory, se všudypřítomný v některých oblastech výpočetního prostředí, ale není nutné porozumět základům tohoto pole.
Pro zúčastněný čtenář doporučujeme přečíst si jednu z referenčních knih, které jsou k dispozici v tématu, [kde najdete další informace](xref:microsoft.quantum.more-information).

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a>Sekvence pro bránu Q # rovnající se státům
Konečný bod vyvolal informace o zápisu na základě teček a programovací jazyk Q #: na začátku tohoto dokumentu jsme zjistili, že stav je základní objekt informací v výpočetním prostředí.  Pak může nastat jako neočekávaně v Q # neexistuje žádný pojem stát.  Místo toho jsou všechny stavy popsány pouze pomocí operací, které slouží k jejich přípravě.  Předchozí příklad představuje vynikající ilustraci.  Místo toho, abychom v registru vyjádřili jednotnou polohu před každým bitem, můžeme výsledek vyjádřit jako $H ^ {\otimes n } \ket{0 } $.  Tento exponenciálně kratší popis stavu má nejen výhodu, že se na něj dá klasický důvod, ale také stručně definuje operace, které je potřeba rozšířit prostřednictvím softwarového zásobníku, aby se tento algoritmus implementoval.  Z tohoto důvodu je Q # navržený tak, aby vygeneroval sekvence brány místo nestavových stavů. na teoretické úrovni jsou však dva perspektivy ekvivalentní.
