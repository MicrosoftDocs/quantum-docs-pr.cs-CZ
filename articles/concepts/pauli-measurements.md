---
title: Pauli měření
description: Naučte se pracovat s operacemi měření jednoduchých a qubit Pauli.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
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
ms.openlocfilehash: 7f10c4ad5eb325da97552d60ff47ea89a699f08d
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269469"
---
# <a name="pauli-measurements"></a>Pauli měření

V předchozích diskusích jsme se zaměřili na výpočetní základní měření.
Ve skutečnosti existují další běžná měření, ke kterým dochází v množství náročném na výpočetní výkon, který je ze zapsaných perspektiv pohodlný, aby se vyjádřily na základě výpočetních měření.
Při práci s Q # se nejběžnější druh měření, na který budete spouštět, pravděpodobně *Pauli měřením*, která generalizace výpočetního základu zahrnuje měření v jiných základech, a parity mezi různými qubits.
V takových případech je běžné projednávat měření Pauli operátoru, a to obecně operátor, jako je $X, Y, Z $ nebo $Z \otimes Z, x \otimes X, x \otimes Y $ a tak dále.

> [!TIP]
> V Q # jsou operátory qubit Pauli obvykle zastoupeny poli typu `Pauli[]` .
> Například pro reprezentaci $X \otimes Z \otimes Y $ lze použít pole `[PauliX, PauliZ, PauliY]` .

Projednávání měření v rámci Pauli operátorů je zvlášť běžné v podpoli s opravou chyb pro každé z nich.
V Q # sledujeme podobnou konvenci. nyní vysvětlujeme toto alternativní zobrazení měření.

Než se pustíte do detailů o tom, jak si představit Pauli měření, je vhodné se seznámit s tím, jak měření jedné qubit v rámci počítače ve státě
Představte si, že máme $n $ qubit, a pak si jednou z nich odqubit pravidla $ , která můžou být ve stavu.
Jinými slovy, měření rozloží stav na jednu ze dvou polovičních mezer.
Můžeme zobecnit způsob, jak si myslíme na měření, aby odrážel tento Intuition.

Pro výstižnější identifikaci těchto podprostorů potřebujeme jazyk, který popisuje jejich popis.
Jedním ze způsobů, jak popsání dvou podprostorů, je jejich zadání prostřednictvím matrice, která má pouze dvě jedinečné eigenvalues, kterou zabere konvence $ \Pm 1 $ .
Jednoduchým příkladem popisujících mezery tímto způsobem je zvážit $Z $ :

$ $ \begin{align}
  Z & = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } .
\end{align}
$$

Po přečtení diagonálních prvků matice Pauli-$Z $ vidíte, že $Z $ má dvě eigenvectors, $ \ket{0 } $ a $ \ket{1 } $, s odpovídajícím eigenvalues $ \Pm 1 $ .
Proto pokud měříme qubit a získáme `Zero` (odpovídající stavu $ \ket{0 } $), víme, že stav našeho qubit je $ + 1 $ eigenstate $ operátoru $Z.
Podobně, pokud získáme `One` , víme, že stav našeho qubit je $-1 $ eigenstate z $Z $ .
Tento proces se označuje v jazyce Pauli měření jako "měřicí Pauli $Z $ a je zcela ekvivalentní k provádění výpočetních měření.

Každá \times matice $2 2 $ , která představuje jednotnou transformaci $Z $ také splňuje tato kritéria.
To znamená, že můžeme také použít matici $A = U ^ \dagger Z $ , kde $U $ je jakákoli jiná Jednotková matice, a poskytnout tak matrici, která definuje dva výsledky měření v jeho eigenvectors $ \Pm 1 $ .
Zápis měření Pauli odkazuje na tuto jednotnou rovnocennost tím, že identifikuje $X, Y, Z $ měření jako ekvivalentní měření, které může udělat pro získání informací z qubit.
Tato měření jsou uvedena níže pro usnadnění práce.


|Pauli měření  |Jednotná transformace  |
|-------------------|------------------------|
| $Z$               | $ \boldone$             |
| $X$               | $H$                    |
| $Y$               | $HS ^ {\dagger}$         |

To znamená, že s použitím tohoto jazyka je "Measure $Y $ " ekvivalentem použití $HS ^ \dagger $ a pak měření v výpočetních intervalech, kde [`S`](xref:microsoft.quantum.intrinsic.s) se jedná o vnitřní operaci na základě fáze, která se někdy označuje jako "brána", a může být simulována jednotnou maticí.

$ $ \begin{align}
    S = \begin{bmatrix}
        1 & 0 \\ \\ 0 & \end{ bmatrix } .
\end{align}
$$

Je také ekvivalentní použít $HS ^ \dagger $ na vektor stavu a pak měření $Z $ , takže následující operace je ekvivalentní `Measure([PauliY], [q])` :

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

Správný stav by se pak našel tak, že transformuje zpět na výpočetní základ, který se musí použít $SH $ na vektor stavu. ve výše uvedeném fragmentu kódu je transformace zpět na výpočetní základ zpracována automaticky pomocí `within … apply` bloku.

V Q # říkáme výsledek---to znamená, že klasické informace extrahované z interakce se stavem---jsou předány `Result` hodnotou $j \in \\ {\Texttt{Zero } , \texttt{One } \\ } $, která označuje, jestli je výsledek v $ (-1) ^ j $ eigenspace operátoru Pauli měřený.


## <a name="multiple-qubit-measurements"></a>Měření s více qubit

Měření qubitch operátorů Pauli je definováno podobně, jak je vidět na základě těchto možností:

$ $ Z \otimes z = \begin{ bmatrix } 1 &0 &0&0 \\\\ 0 & -1&0&0 \\\\ 0&0 & -1&0 \\\\ 0&0&0&1 \end{bmatrix} .
$$

Proto tensor produkty dvou operátorů Pauli-$Z $ tvoří matici složenou ze dvou mezer, které se skládají z $ + 1 $ a $-1 $ eigenvalues.
Stejně jako u jediného qubit, představuje obojí prostor, což znamená, že polovina přístupného vektorového prostoru patří do $ + 1 $ eigenspace a zbylé polovině do $-1 $ eigenspace.
Obecně je snadné vidět z definice tensor produktu, že tensor produkt Pauli-$Z $ a identita se taky řídí.
Třeba

$ $ \begin{align}
    Z \otimes \boldone = \begin{bmatrix}
        1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 &-1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{ bmatrix } .
\end{align}
$$

Stejně jako v případě jakékoli jednotkové transformace těchto matic také popisuje dvě poloviční prostory označené pomocí $ \Pm 1 $ eigenvalues.
Například $X \otimes X = h h \otimes (z \otimes ) h \otimes h $ od identity, kterou $Z = HXH $ .
Podobně jako u qubitového případu je možné všechny qubit Pauli-měření zapsat jako $U ^ \dagger (Z \otimes \id) u $ pro $4 \times 4 $ jednotkové matice $U $ . Vytvoříme výčet transformací v následující tabulce.

> [!NOTE]
> V tabulce níže používáme $ \operatorname{SWAP } $ k označení matice $ $ \begin{align.}
>     \operatorname{SWAP } & = \left (\begin{Matrix}
>         1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{Matrix } \right) \end{align}
> $ $ používá se k simulaci vnitřní operace [`SWAP`](xref:microsoft.quantum.intrinsic) .

|Pauli měření     |Jednotná transformace  |
|----------------------|------------------------|
| $Z \otimes \boldone$ | $ \boldone \otimes \boldone$ |
| $Z \otimes \boldone$ | $ \boldone \otimes \boldone$ |
| $X \otimes \boldone$ | $H \otimes \boldone$ |
| $Y \otimes \boldone$ | $HS ^ \dagger \otimes \boldone$ |
| $ \boldone \otimes Z$ | $ \operatorname{SWAP}$ |
| $ \boldone \otimes X$ | $ (H \otimes \boldone) \operatorname{swap}$ |
| $ \boldone \otimes Y$ | $ (HS ^ \dagger \otimes \boldone) \operatorname{swap}$ |
| $Z \otimes Z$ | $ \operatorname{CNOT } \_ {10}$ |
| $X \otimes Z$ | $ \operatorname{CNOT } \_ {10 } (H \otimes \boldone) $ |
| $Y \otimes Z$ | $ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes \boldone) $ |
| $Z \otimes X$ | $ \operatorname{CNOT } \_ {10 } (\boldone \otimes H) $ |
| $X \otimes X$ | $ \operatorname{CNOT } \_ {10 } (H \otimes h) $ |
| $Y \otimes X$ | $ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes H) $ |
| $Z \otimes Y$ | $ \operatorname{CNOT } \_ {10 } (\boldone \otimes HS ^ \dagger) $ |
| $X \otimes Y$ | $ \operatorname{CNOT } \_ {10 } (H \otimes HS ^ \dagger) $ |
| $Y \otimes Y$ | $ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes HS ^ \dagger) $ |

Tato [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operace se zobrazí z následujícího důvodu.
Každé měření Pauli, které neobsahuje matrici $ \boldone, $ je ekvivalentní až do $Z \otimes Z $ výše uvedeného důvodu.
Eigenvalues z $Z \otimes z $ pouze závisí na paritě qubits, která zahrnuje každý výpočetní vektor a kontrolované – nečinnosti slouží k výpočtu této parity a jejich uložení v prvním bitu.
Po měření prvního bitu můžeme obnovit identitu výsledného prostoru, který je ekvivalentní k měření Pauli operátoru.

Další Poznámka: i když je možné předpokládat, že měření $Z \otimes Z $ je stejné jako při sekvenčním měření $Z \otimes \mathbb{1 } $ a pak $ \mathbb{1 } \otimes Z $ , tento předpoklad by byl nepravdivý.
Důvodem je, že měření $Z \otimes z $ projektuje stav neeigenstateu na $ + 1 $ nebo $-1 $ pro tyto operátory.
Měření $Z \otimes \mathbb{1 } $ a pak $ \Mathbb{1 } \otimes Z $ projektuje vektor stavu v polovině na polovinu prostoru $Z \otimes \mathbb{1 } $ a pak na polovinu prostoru $ \mathbb{1 } \otimes Z $ . Vzhledem k tomu, že jsou k dispozici čtyři výpočetní vektory, může použití obou měření snížit stav na čtvrtinové místo a tím se sníží na jeden vektor výpočetního základu.

## <a name="correlations-between-qubits"></a>Korelace mezi qubits
Další možností, jak se podívat na měření tensor produktů Paulich matric, \otimes jako $ je $X X nebo $Z \otimes Z $ , je, že tato měření vám umožní podívat se na informace, které jsou uložené v korelaci mezi dvěma qubits.
Měření $X \otimes \id $ vám umožní podívat se na informace, které jsou místně uložené v první qubit.
I když jsou oba typy měření stejně cenné při práci ve výpočetním prostředí, bývalé osvětlení síly při práci.
To znamená, že ve výpočetním prostředí se často informace, které chcete vědět, neukládají do žádného qubit, ale místo toho, aby se ukládaly do všech qubits najednou, a proto jenom pomocí společného měření (např. $Z \otimes Z $ ) se tyto informace stanou manifestem.

Například při opravě chyb často chceme zjistit, k jaké chybě došlo při učení o stavu, který se snažíte chránit.
[Ukázka bitového překlápění kódu](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) ukazuje příklad toho, jak to lze provést pomocí měření, jako je $Z \otimes Z \otimes \id $ a $ \id \Otimes Z \otimes z $ .
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

Lze také změřit libovolné Pauli operátory, jako je například $X \otimes Y \Otimes Z \otimes \boldone $ .
Všechny takové tensor produkty operátorů Pauli mají pouze dvě eigenvalues $ \Pm 1 $ a oba eigenspaces představují poloviční prostory celého vektorového prostoru.
Proto se shodují s výše uvedenými požadavky.

V Q # taková měření vrací $j, $ Pokud měření vyplývají z výsledku eigenspace Sign $ (-1) ^ j $ .
Pauli měření jako integrovaná funkce v Q # je užitečná, protože měření takových operátorů vyžaduje dlouhé řetězy řízených a nevratných operací a základní transformace, které popisují $U diagonalizingou bránu, která je potřeba k tomu, aby se $ operace mohla vyjádřit jako tensor produkt $Z $ a $ \id $ . Díky možnosti určit, že chcete provést jedno z těchto předdefinovaných měření, nemusíte si dělat starosti s tím, jak transformovat svůj základ, aby výpočetní základní měření poskytovalo potřebné informace.
Q # zpracovává všechny potřebné transformace automaticky pro vás.
Další informace najdete v tématu [`Measure`](xref:microsoft.quantum.intrinsic.measure) operace a [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) .

## <a name="the-no-cloning-theorem"></a>Věta bez klonování

Informace o nemocném případě jsou výkonné.
Umožňuje nám dělat úžasné věci, jako jsou čísla faktorů exponenciálně rychleji než nejlepší známé klasické algoritmy, nebo efektivně simulovat korelační elektronické systémy, které Classic potřebují k přesnému simulaci exponenciálních nákladů.
Existují však určitá omezení výkonu s využitím nároku na výpočetní výkon.
Jedno takové omezení je dáno *větaem bez klonování*.

Věta pro No-klonování není aptly pojmenováno.
Neumožňuje klonování obecných stavových stavů počítačem s více než jednou.
Důkaz věta je výjimečně přímočarý.
I když je úplný důkaz věta bez klonování pro naši diskuzi příliš technický, důkaz v případě žádného dalšího pomocného qubitsu v rámci našeho rozsahu (pomocné qubits se qubits používá pro pomocné místo během výpočtu a snadno se používá a spravuje v Q # najdete v tématu [výpůjčka qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).

V případě takového počítače s více operačními systémem musí být operace klonování popsána jednotnou maticí.
Nezakážeme měření, protože by došlo k poškození stavu, který se snažíme klonovat.
Pro simulaci operace klonování chceme, aby jednotná matice používala vlastnost, která je $ $ U \ket { \psi } \ket{0 } = \ket { \psi } \ket { \psi}
$ $ for any State $ \ket { \psi } $.
Vlastnost linearity matice násobení pak znamená, že pro jakýkoliv druhý stav 2 – 2 – { 2 } $ \ket \phi $,

$ $ \begin{align}
    U \left [\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right] \ket{0}
    & = \frac{1 } {\sqrt{2 } } U \ket { \phi } \ket{0}
      + \frac{1 } {\sqrt{2 } } U \ket { \psi } \ket{0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \left (\ket { \phi } \ket { \phi } + \ket { \psi } \ket { \psi}
        \right) \\ \\ & \Ne \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right) \otimes \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right).
\end{align}
$$

To poskytuje základní Intuition za věta bez klonování: každé zařízení, které kopíruje neznámý stav, musí způsobit chyby alespoň u některých stavů, které kopíruje.
I když klíč předpokládá, že Cloner funguje lineárně na vstupním stavu, může být porušená přidáním a měřením pomocných qubits, takže tyto interakce také nevrací informace o systému prostřednictvím statistik měření a zabrání v takových případech přesné klonování.
Další [informace](xref:microsoft.quantum.more-information)o tom, jak se věta bez klonování, najdete v tématu.

Věta bez klonování je důležité pro kvalitativní porozumění výpočetním procesorům, protože pokud byste mohli naklonovat stavy nenákladných stavových procesorů, pak by vám byla udělena téměř Magical možnost učit se ze států.
Ve skutečnosti byste mohli narušit zásadu nejistoty Heisenberg vaunted.
Alternativně můžete použít optimální Cloner k získání jedné ukázky ze složitosti distribuce nečinnosti a zjistit všechno, co byste se mohli dozvědět o této distribuci jenom z jedné ukázky.
To by vypadalo jako převrácení mince a pozorování hlav a následného oznámení o tom, že na výsledek má odpovědět "Ah. rozdělení této mince musí být Bernoulliho s $p = 0.512643 \ ldots $ !"  Takový příkaz by nebyl sensical, protože jeden z bitových informací (výsledek hlav) jednoduše nemůže poskytnout mnoho informací potřebných ke kódování distribuce bez podstatných předchozích informací.
Podobně bez předchozích informací nemůžeme zcela klonovat stav, protože nemůžeme připravit komplet těchto mincí, aniž by bylo potřeba znát $p $ .

Informace nejsou v výpočetním prostředí bezplatné.
Každá qubit měřená má jedinou bitovou informaci a věta bez klonování ukazuje, že není k dispozici žádné zadní vrátka, které by bylo možné zneužít k získání základních kompromisů mezi informacemi získanými v systému a vyvolaným poruchou.
