---
title: Pauli měření
description: Naučte se pracovat s operacemi měření jednoduchých a qubit Pauli.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 08babbcb0d6c6c4d83622489bc4ecc811e64829a
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320871"
---
# <a name="pauli-measurements"></a>Pauli měření

V předchozích diskusích jsme se zaměřili na výpočetní základní měření.
Ve skutečnosti existují další běžná měření, ke kterým dochází v množství náročném na výpočetní výkon, který je ze zapsaných perspektiv pohodlný, aby se vyjádřily na základě výpočetních měření.
Při práci s Q # se nejběžnější druh měření, na který budete spouštět, pravděpodobně *Pauli měřením*, která generalizace výpočetního základu zahrnuje měření v jiných základech, a parity mezi různými qubits.
V takových případech je běžné projednávat měření Pauli operátoru, a to obecně operátor, například $X, Y, Z $ nebo $Z \otimes Z, X\otimes X, X\otimes Y $ a tak dále.

> [!TIP]
> V Q # jsou operátory qubit Pauli obvykle zastoupeny poli typu `Pauli[]`.
> Například pro reprezentaci $X \otimes Z \otimes Y $ můžete použít pole `[PauliX, PauliZ, PauliY]`.

Projednávání měření v rámci Pauli operátorů je zvlášť běžné v podpoli s opravou chyb pro každé z nich.
V Q # sledujeme podobnou konvenci. nyní vysvětlujeme toto alternativní zobrazení měření.

Než se pustíte do detailů o tom, jak si představit Pauli měření, je vhodné se seznámit s tím, jak měření jedné qubit v rámci počítače ve státě
Představte si, že máme $n $-qubitský stav; pak se jednou z nich odměří jedna qubit, což je polovina možností $2 ^ n $, které by mohly být ve stavu.
Jinými slovy, měření rozloží stav na jednu ze dvou polovičních mezer.
Můžeme zobecnit způsob, jak si myslíme na měření, aby odrážel tento Intuition.

Pro výstižnější identifikaci těchto podprostorů potřebujeme jazyk, který popisuje jejich popis.
Jedním ze způsobů, jak popsání dvou podprostorů, je jejich zadání prostřednictvím matrice, která má pouze dvě jedinečné eigenvalues, kterou zabere konvence $ \Pm $1.
Pro jednoduchý příklad popisujících mezery tímto způsobem zvažte $Z $:

$ $ \begin{align} Z & = \begin{bmatrix} 1 & 0 \\\\ 0 &-1 \end{bmatrix}.
\end{align} $ $

Po přečtení diagonálních prvků Pauli-$Z $ se můžeme podívat, že $Z $ má dvě eigenvectors, $ \ket{0}$ a $ \ket{1}$, s odpovídajícím eigenvalues $ \Pm $1.
Proto pokud měříme qubit a získáme `Zero` (odpovídající stavu $ \ket{0}$), víme, že stav našeho qubit je $ + $1 eigenstate operátoru $Z $.
Podobně pokud získáme `One`, víme, že stav našeho qubit je $-$1 eigenstate $Z $.
Tento proces se označuje v jazyce Pauli měření jako "měřicí Pauli $Z $ a je zcela ekvivalentní k provádění výpočetních měření.

Všechna tato kritéria jsou v každé matrici $2 \ krát $2, která představuje jednotnou transformaci $Z $, také splňuje.
To znamená, že můžeme také použít matrici $A = U ^ \dagger Z, kde $U $ je jakákoli jiná Jednotková matice, a poskytnout tak matrici, která definuje dva výsledky měření v jeho $ \Pm $1 eigenvectors.
Zápis Pauli měření odkazuje na tuto jednotnou odchylku tím, že identifikuje $X, Y, Z $ měření jako ekvivalentní měření, které může získat informace z qubit.
Tato měření jsou uvedena níže pro usnadnění práce.


|Pauli měření  |Jednotná transformace  |
|-------------------|------------------------|
| $Z $               | $ \boldone $             |
| $X $               | $H $                    |
| $Y $               | $HS ^ {\dagger} $         |

To znamená, že s použitím tohoto jazyka je "Measure $Y $" ekvivalentem použití $HS ^ \dagger $ a pak se měří v výpočetním základu, kde [`S`](xref:microsoft.quantum.intrinsic.s) je vnitřní operace pro práci s procesorem, která se někdy nazývá "brána" a může být simulována jednotnou maticí.

$ $ \begin{align} S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.
\end{align} $ $

Je také ekvivalentní použít $HS ^ \dagger $ na vektor stavu a pak měření $Z $, aby následující operace byla rovnocenná `Measure([PauliY], [q])`:

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

Správný stav by se pak našel tak, že transformuje zpátky na výpočetní základ, který se použije k použití $SH $ na stavový vektor. ve výše uvedeném fragmentu kódu je transformace zpět na výpočetní základ zpracována automaticky pomocí `within … apply`ho bloku.

V Q # říkáme výsledek---to znamená, že klasické informace extrahované z interakce se stavem---jsou předány `Result` hodnotě $j \in \\{\texttt{Zero}, \texttt{One}\\} $, která označuje, jestli je výsledek v $ (-1) ^ j $ eigenspace pro měřený Pauli operátor.


## <a name="multiple-qubit-measurements"></a>Měření s více qubit

Měření qubitch operátorů Pauli je definováno podobně, jak je vidět na základě těchto možností:

$ $ Z\otimes Z = \begin{bmatrix}1 & 0 & 0 & 0\\\\ 0 &-1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 & 1 \ konec {bmatrix}.
$$

Proto tensor produkty dvou operátorů Pauli-$Z $ tvoří matici tvořenou dvěma mezerami, které se skládají z $ + $1 a $-$1 eigenvalues.
Stejně jako u jediného qubit, představuje obojí prostor, což znamená, že polovina přístupného vektorového prostoru patří do $ + $1 eigenspace a zbylé polovině k $-$1 eigenspace.
Obecně se dá snadno zobrazit z definice tensor produktu, že se jedná o tensor produkt Pauli-$Z $ a identitu taky dodržuje tyto informace.
Například:

$ $ \begin{align} Z \otimes \boldone = \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 &-1 & 0 \\\\ 0 & 0 & 0 &-1 \end{bmatrix}.
\end{align} $ $

Stejně jako v případě jakékoli jakékoli jednotkové transformace těchto matic také popisuje dvě poloviční prostory označené pomocí $ \Pm $1 eigenvalues.
Například $X \otimes X = H\otimes H (Z\otimes Z) H\otimes H $ z identity, která $Z = HXH $.
Podobně jako u qubitového případu můžete všechna qubit Pauli-měření zapsat jako $U ^ \dagger (Z\otimes \id) U $ pro $4 \ krát $4 jednotkových matric $U $. Vytvoříme výčet transformací v následující tabulce.

> [!NOTE]
> V následující tabulce uvádíme pomocí $ \operatorname{SWAP} $ maticí $ $ \begin{align} \operatorname{SWAP} & = \left (\begin{Matrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{Matrix}\right) \end{align} $ $, která se používá k simulaci vnitřní operace [`SWAP`](xref:microsoft.quantum.intrinsic).

|Pauli měření     |Jednotná transformace  |
|----------------------|------------------------|
| $Z \otimes \boldone $ | $ \boldone \otimes \boldone $ |
| $Z \otimes \boldone $ | $ \boldone\otimes \boldone $ |
| $X \otimes \boldone $ | $H \otimes \boldone $ |
| $Y \otimes \boldone $ | $HS ^ \dagger\otimes \boldone $ |
| $ \boldone \otimes Z $ | $ \operatorname{SWAP} $ |
| $ \boldone \otimes X $ | $ (H\otimes \boldone) \operatorname{SWAP} $ |
| $ \boldone \otimes Y $ | $ (HS ^ \dagger\otimes \boldone) \operatorname{SWAP} $ |
| $Z \otimes Z $ | $ \operatorname{CNOT}\_{10}$ |
| $X \otimes Z $ | $ \operatorname{CNOT}\_{10}(H\otimes \boldone) $ |
| $Y \otimes Z $ | $ \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes \boldone) $ |
| $Z \otimes X $ | $ \operatorname{CNOT}\_{10}(\boldone\otimes H) $ |
| $X \otimes X $ | $ \operatorname{CNOT}\_{10}(H\otimes H) $ |
| $Y \otimes X $ | $ \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes H) $ |
| $Z \otimes Y | $ \operatorname{CNOT}\_{10}(\boldone \otimes HS ^ \dagger) $ |
| $X \otimes Y | $ \operatorname{CNOT}\_{10}(H\otimes HS ^ \dagger) $ |
| $Y \otimes Y | $ \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes HS ^ \dagger) $ |

Tady se [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operace objeví z následujícího důvodu.
Každé měření Pauli, které neobsahuje matrici $ \boldone $, je ekvivalentní až s jednou jednotkou $Z \otimes Z $ výše uvedenými důvody.
Eigenvalues $Z \otimes Z $ závisí pouze na paritě qubits, která zahrnuje každý výpočetní vektor a kontrolované – nečinnosti slouží k výpočtu této parity a jejich uložení v prvním bitu.
Po měření prvního bitu můžeme obnovit identitu výsledného prostoru, který je ekvivalentní k měření Pauli operátoru.

Další Poznámka: v takovém případě může být nutné předpokládat, že měření $Z \otimes Z $ je stejné jako sekvenční měření $Z \otimes \mathbb{1}$ a pak $ \mathbb{1} \otimes Z $, tento předpoklad by byl nepravdivý.
Důvodem je to, že měření $Z \otimes Z $ projekty se stavem do $ + $1 nebo $-$1 eigenstate těchto operátorů.
Měření $Z \otimes \mathbb{1}$ a pak $ \mathbb{1} \otimes Z $ Projects (stavová část) se předá na polovinu místa $Z \otimes \mathbb{1}$ a pak na polovinu prostoru $ \mathbb{1} \otimes Z $.
Vzhledem k tomu, že jsou k dispozici čtyři výpočetní vektory, může použití obou měření snížit stav na čtvrtinové místo a tím se sníží na jeden vektor výpočetního základu.

## <a name="correlations-between-qubits"></a>Korelace mezi qubits
Další možností, jak se podívat na měření tensor produktů Paulich matric, jako je $X \otimes X $ nebo $Z \otimes Z $, je to, že tato měření vám umožní podívat se na informace, které jsou uložené v korelaci mezi dvěma qubits.
Měření $X \otimes \id $ vám umožní podívat se na informace, které jsou místně uložené v prvním qubit.
I když jsou oba typy měření stejně cenné při práci ve výpočetním prostředí, bývalé osvětlení síly při práci.
To znamená, že ve výpočetním prostředí se často informace, které chcete zjistit, neukládají do žádného qubit, ale místo toho, aby se ukládaly do všech qubits najednou, a proto jenom pomocí společného měření (např. $Z \otimes Z $) informace se stanou manifestem.

Například při opravě chyb často chceme zjistit, k jaké chybě došlo při učení o stavu, který se snažíte chránit.
[Ukázka bitového překlápění kódu](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) ukazuje příklad toho, jak to lze provést pomocí měření, jako je $Z \otimes Z \otimes \id $ a $ \Id \otimes Z \otimes z $.
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

Lze také změřit libovolné Pauli operátory, jako je například $X \otimes Y \otimes Z \otimes \boldone $.
Všechny takové produkty tensor operátorů Pauli mají pouze dva eigenvalues $ \Pm $1 a oba eigenspaces představují poloviční prostory celého vektorového prostoru.
Proto se shodují s výše uvedenými požadavky.

V Q # taková měření vrací $j $, pokud měření vyplývají z výsledku eigenspace Sign $ (-1) ^ j $.
Pauli měření jako integrovaná funkce v Q # je užitečná, protože měření takových operátorů vyžaduje dlouhé řetězy řízených a nevratných operací a základní transformace, které popisují diagonalizingou bránu $U $, která je potřeba k tomu, aby se operace mohla vyjádřit jako tensor produkt $Z $ a $ \id $.
Díky možnosti určit, že chcete provést jedno z těchto předdefinovaných měření, nemusíte si dělat starosti s tím, jak transformovat svůj základ, aby výpočetní základní měření poskytovalo potřebné informace.
Q # zpracovává všechny potřebné transformace automaticky pro vás.
Další informace najdete v tématu operace [`Measure`](xref:microsoft.quantum.intrinsic.measure) a [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) .

## <a name="the-no-cloning-theorem"></a>Věta bez klonování

Informace o nemocném případě jsou výkonné.
Umožňuje nám dělat úžasné věci, jako jsou čísla faktorů exponenciálně rychleji než nejlepší známé klasické algoritmy, nebo efektivně simulovat korelační elektronické systémy, které Classic potřebují k přesnému simulaci exponenciálních nákladů.
Existují však určitá omezení výkonu s využitím nároku na výpočetní výkon.
Jedno takové omezení je dáno *větaem bez klonování*.

Věta pro No-klonování není aptly pojmenováno.
Neumožňuje klonování obecných stavových stavů počítačem s více než jednou.
Důkaz věta je výjimečně přímočarý.
Úplný důkaz věta bez klonování je pro naši diskuzi příliš technický, proto se v rámci našeho oboru nejedná o důkaz, že v případě žádného dalšího pomocného qubitsu není v našem rozsahu (pomocné qubits se qubits používá pro pomocné místo během výpočtu a dají se snadno použít a spravovat v Q #, viz <xref:microsoft.quantum.techniques.qubits>).

V případě takového počítače s více operačními systémem musí být operace klonování popsána jednotnou maticí.
Nezakážeme měření, protože by došlo k poškození stavu, který se snažíme klonovat.
Pro simulaci operace klonování chceme, aby jednotná matice používala vlastnost $ $ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi} $ $ pro jakýkoliv stav $ \ket{\psi} $.
Vlastnost linearity matice násobení pak znamená, že pro jakýkoliv druhý stav 2 – 2 \ket{\phi} $,

$ $ \begin{align} U \left [\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right] \ket{0} & = \frac{1}{\sqrt{2}} U\ket {\ fí} \ KET{0} + \frac{1}{\sqrt{2}} U\ket {\ psí} \ KET{0} \\\\ & = \frac{1}{\sqrt{2}} \left (\ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi} \right) \\\\ & \Ne \left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right) \otimes \ Left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right).
\end{align} $ $

To poskytuje základní Intuition za věta bez klonování: každé zařízení, které kopíruje neznámý stav, musí způsobit chyby alespoň u některých stavů, které kopíruje.
I když klíč předpokládá, že Cloner funguje lineárně na vstupním stavu, může být porušená přidáním a měřením pomocných qubits, takže tyto interakce také nevrací informace o systému prostřednictvím statistik měření a zabrání přesnému v takových případech se klonuje také.
Další [informace](xref:microsoft.quantum.more-information)o tom, jak se věta bez klonování, najdete v tématu.

Věta bez klonování je důležité pro kvalitativní porozumění výpočetním procesorům, protože pokud byste mohli naklonovat stavy nenákladných stavových procesorů, pak by vám byla udělena téměř Magical možnost učit se ze států.
Ve skutečnosti byste mohli narušit zásadu nejistoty Heisenberg vaunted.
Alternativně můžete použít optimální Cloner k získání jedné ukázky ze složitosti distribuce nečinnosti a zjistit všechno, co byste se mohli dozvědět o této distribuci jenom z jedné ukázky.
To by vypadalo jako převrácení mince a pozorování hlav a následného oznámení o tom, že na výsledek má odpovědět "Ah. rozdělení této mince musí být Bernoulliho s $p = 0.512643 \ ldots $!"  Takový příkaz by nebyl sensical, protože jeden z bitových informací (výsledek hlav) jednoduše nemůže poskytnout mnoho informací potřebných ke kódování distribuce bez podstatných předchozích informací.
Podobně bez předchozích informací nemůžeme zcela klonovat stav, protože nemůžeme připravit komplet těchto mincí bez znalosti $p $.

Informace nejsou v výpočetním prostředí bezplatné.
Každá qubit měřená má jedinou bitovou informaci a věta bez klonování ukazuje, že není k dispozici žádné zadní vrátka, které by bylo možné zneužít k získání základních kompromisů mezi informacemi získanými v systému a vyvolaným poruchou.
