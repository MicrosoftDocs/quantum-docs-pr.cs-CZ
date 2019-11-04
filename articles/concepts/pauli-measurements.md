---
title: Měření Pauli | Microsoft Docs
description: Pauli měření
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7bea821be7e26e72f2860278486d35be676ca63d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183705"
---
# <a name="pauli-measurements"></a>Pauli měření

V předchozích diskusích jsme se zaměřili na výpočetní základní měření.  Ve skutečnosti jsou k dispozici další běžná měření, ke kterým dochází v množství náročném na výpočetní výkon, který je ze zapsaných perspektiv pohodlný, a to v souvislosti s výpočetními základními měřeními.  Nejběžnější sadou těchto měření jsou *Pauli měření*.  V takových případech je běžné projednávat měření Pauli operátoru, a to obecně operátor, například $X, Y, Z $ nebo $Z \otimes Z, X\otimes X, X\otimes Y $ a tak dále.  Projednávání měření v rámci Pauli operátorů je zvlášť běžné v podpoli s opravou chyb pro každé z nich. V Q # sledujeme podobnou konvenci. nyní vysvětlujeme toto alternativní zobrazení měření.

Než se pustíte do detailů o tom, jak si představit Pauli měření, je vhodné se seznámit s tím, jak měření jedné qubit v rámci počítače ve státě  Představte si, že máme $n $-qubitský stav; pak se jednou z nich odměří jedna qubit, což je polovina možností $2 ^ n $, které by mohly být ve stavu.  Jinými slovy, měření rozloží stav na jednu ze dvou polovičních mezer.  Můžeme zobecnit, jak si myslíme o měření, abychom to odráželi.

Pro výstižnější identifikaci těchto podprostorů potřebujeme jazyk, který popisuje jejich popis.  Jedním ze způsobů, jak to provést, je popsat dvě podprostory tak, že je zadáte přes matrici, která má pouze dvě jedinečné eigenvalues, kterou používá konvence $ \Pm $1.  Nejjednodušším příkladem je:

$ $ Z = \begin{bmatrix} 1 & 0 \\\\ 0 &-1 \end{bmatrix}.
$$

Pauli-$Z $ Matrix má jasně dvě eigenvectors $ \ket{0}$ a $ \ket{1}$ with eigenvalues $ \Pm $1.  Proto pokud měříme qubit a získáme $ \ket{0}$ máme v sadě $ + $1 eigenspace (sada všech vektorů, které jsou tvořeny součty eigenvectors pouze s pozitivním nebo pouze negativním eigenvaluesm) operátoru a pokud měříme $ \ket{1}$, budeme v $-$1 EI genspace $Z $.  Tento proces se označuje v jazyce Pauli měření jako "měřicí Pauli $Z $" a je zcela stejný jako při provádění výpočetních měření.

Samozřejmě každou matrici $2 \ krát $2, která představuje jednotnou transformaci $Z $, také splňuje tato kritéria.  To znamená, že můžeme také zvážit $A matice = U ^ \dagger Z U $, pro každou jednotkovou matrici $U $, a poskytnout tak matrici, která definuje dva výsledky měření v jeho $ \Pm $1 eigenvectors.  Zápis měření Pauli odkazuje na to tím, že identifikuje $X, Y, Z $ měření jako ekvivalentní měření, které může získat informace z qubit.  Tato měření jsou uvedena níže pro usnadnění práce.

$ $ \begin{Array}{| c | c |} \text{Pauli měření} & U\\\\ Z & \boldone\\\\ X & H\\\\ a & HS ^ \dagger\\\\ \end{Array} $ $

To znamená, že s použitím tohoto jazyka je "Measure $Y $" ekvivalentem použití $HS ^ \dagger $ a pak se měří v výpočetních intervalech, kde $S $ je fáze s názvem, která se nazývá.

$ $ \begin{bmatrix}1 & 0\\\\ 0 & i\end {bmatrix}.
$$

Je také ekvivalentní použít $HS ^ \dagger $ na vektor stavu a pak na měření $Z $.  Správný stav by se pak našel tak, že transformuje zpátky na výpočetní základ, který se použije k použití $SH $ na vektor stavu.

## <a name="q-outcome-classical-information-obtained-from-quantum-state"></a>Výsledky z nestavových souborů Q # byly získány z nepotřebného stavu
V Q # říkáme výsledek, tj. klasické informace extrahované z interakce se stavem, jsou $j $, který je v sadě $\{0, 1\}$, pokud je výsledek v $ (-1) ^ j $ eigenspace operátoru Pauli.

Měření qubitch operátorů Pauli je definováno podobně, jak je vidět na základě těchto možností:

$ $ Z\otimes Z = \begin{bmatrix}1 & 0 & 0 & 0\\\\ 0 &-1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 & 1 \ konec {bmatrix}.
$$

Proto tensor produkty dvou operátorů Pauli-$Z $ tvoří matici tvořenou dvěma mezerami, které se skládají z $ + $1 a $-$1 eigenvalues.  Stejně jako u jediného qubit, představuje obojí prostor, což znamená, že polovina přístupného vektorového prostoru patří do $ + $1 eigenspace a zbylé polovině k $-$1 eigenspace.  Obecně se dá snadno zobrazit z definice tensor produktu, že se jedná o tensor produkt Pauli-$Z $ a identitu taky dodržuje tyto informace.  Například:

$ $ Z\otimes\boldone = \begin{bmatrix} 1 & 0 & 0 & 0\\\\ 0 & 1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 &-1 \ konec {bmatrix}.
$$

Stejně jako v případě jakékoli jakékoli jednotkové transformace těchto matic také popisuje dvě poloviční prostory označené pomocí $ \Pm $1 eigenvalues.  Například $X \otimes X = H\otimes H (Z\otimes Z) H\otimes H $ z identity, která $Z = HXH $.  Podobně jako u qubitového případu můžete všechna qubit Pauli-měření zapsat jako $U ^ \dagger (Z\otimes \id) U $ pro $4 \ krát $4 jednotkových matric $U $.  Vyčíslení transformací v následující tabulce, kde zavádíme pro usnadnění práce s bránou pro zahození, která zaměňuje qubits $0 $ a $1 $: $ \operatorname{SWAP} = \operatorname{CNOT}\_{01}\operatorname{CNOT}\_{10}\operatorname{ CNOT}\_{01}$:

$ $ \begin{Array}{| c | c |} \text{Pauli měření} & U\\\\ \hline Z\otimes \boldone & \boldone\otimes \boldone\\\\ X\otimes \boldone & H\otimes \boldone\\\\ Y\otimes \boldone & HS ^ \dagger\ otimes \boldone\\\\ \boldone \otimes Z & \operatorname{SWAP}\\\\ \boldone \otimes X & (H\otimes \boldone) \operatorname{SWAP}\\\\ \boldone \otimes Y & (HS ^ \dagger\otimes \boldone) \ operator {SWAP}\\\\ Z\otimes Z & \operatorname{CNOT}\_{10}\\\\ X\otimes Z & \operatorname{CNOT}\_{10}(H\otimes \boldone)\\\\ Y\otimes Z & \ operator {CNOT}\_{10}(HS ^ \dagger\otimes \boldone)\\\\ Z\otimes X & \operatorname{CNOT}\_{10}(\boldone\otimes H)\\\\ X\otimes X & \operatorname{CNOT}\_@no__t _31_ (H\otimes H)\\\\ Y\otimes X & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes H)\\\\ Z\otimes Y & \operatorname{CNOT}\_{10}(\boldone \otimes HS ^ \dagger)\\\\ X\otimes Y & \operatorname{CNOT}\_{10}(H\otimes HS ^ \dagger)\\\\ Y\otimes Y & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes HS ^ \dagger)\\\\ \end{Array} $ $

Z následujícího důvodu se zobrazí okno Brána $ \operatorname{CNOT}\_{10}$.  Každé měření Pauli, které neobsahuje matrici $ \boldone $, je ekvivalentní až s jednou jednotkou $Z \otimes Z $ výše uvedenými důvody.  Eigenvalues $Z \otimes Z $ závisí pouze na paritě qubits, která zahrnuje každý výpočetní vektor a kontrolované – nečinnosti, které se zobrazují v tomto seznamu, k výpočtu této parity a jejich uložení v prvním bitu.  Po měření prvního bitu můžeme obnovit identitu výsledného prostoru, který je ekvivalentní k měření Pauli operátoru.

Jedna další Poznámka, i když se může stát, že měření $Z \otimes Z $ je stejné jako měření $Z \otimes \id $ a pak $ \id \otimes Z $, tento předpoklad by byl nepravdivý.  Důvodem je to, že měření $Z \otimes Z $ projekty se stavem do $ + $1 nebo $-$1 eigenstate těchto operátorů.  Měření $Z \otimes \id $ a pak $ \id \otimes Z $ projekty se vektorem stavu napředí na polovinu prostoru $Z \otimes \id $ a pak na poloviční prostor z $ \id \otimes Z $.  Vzhledem k tomu, že jsou k dispozici čtyři výpočetní vektory, může použití obou měření snížit stav na čtvrtinové místo a tím se sníží na jeden vektor výpočetního základu.


## <a name="correlations-between-qubits"></a>Korelace mezi qubits
Další možností, jak se podívat na měření tensor produktů Paul, například $X \otimes X $ nebo $Z \otimes Z $, je, že tato měření vám umožní podívat se na informace, které jsou uložené v korelaci mezi dvěma qubitsy.  Měření $X \otimes \id $ vám umožní podívat se na informace, které jsou místně uložené v prvním qubit.  I když jsou oba typy měření stejně cenné při práci ve výpočetním prostředí, bývalé osvětlení síly při práci. To znamená, že v případě velmi náročného výpočetního prostředí se informace, které chcete vědět, neukládají do žádného qubit, ale místo toho, aby se ukládaly do všech qubits najednou, a jenom tak, že je prohlížíte pomocí společného měření s $Z \otimes Z $ se tyto informace stanou zřetel.

Lze také změřit libovolné Pauli operátory, jako je například $X \otimes Y \otimes Z \otimes \boldone $.  Všechny takové produkty tensor operátorů Pauli mají pouze dva eigenvalues $ \Pm $1 a oba eigenspaces představují poloviční prostory celého vektorového prostoru.  Proto se shodují s výše uvedenými požadavky.

V Q # taková měření vrací $j $, pokud měření vyplývají z výsledku eigenspace Sign $ (-1) ^ j $.  To je užitečné v případě, že je předdefinovaná funkce v Q # užitečná, protože měření takových operátorů vyžaduje dlouhé řetězy řízených a nevratných operací a základní transformace, které popisují diagonalizingou bránu $U $, která je potřeba k tomu, aby se operace mohla vyjádřit jako tensor $Z $ a $ \id $.  Když jednoduše určíte, že chcete provést jedno z těchto předdefinovaných měření, nemusíte si dělat starosti s tím, jak transformovat svůj základ, aby měření na základě výpočtů poskytovalo potřebné informace.  Q # zpracovává všechny potřebné transformace automaticky pro vás. Pauli měření najdete v tématu [Referenční dokumentace knihovny Q #](/qsharp/api/canon/microsoft.quantum.canon.measurepaulis)

## <a name="the-no-cloning-theorem"></a>Věta bez klonování
Informace o nemocném případě jsou výkonné.  Umožňuje nám dělat úžasné věci, jako jsou čísla faktorů exponenciálně rychleji než nejlepší známé klasické algoritmy, nebo efektivně simulovat korelační elektronické systémy, které Classic potřebují k přesnému simulaci exponenciálních nákladů.  Existují však určitá omezení výkonu s využitím nároku na výpočetní výkon.  Jedno takové omezení je dáno *větaem bez klonování*.

Věta pro No-klonování není aptly pojmenováno.
Neumožňuje klonování obecných stavových stavů počítačem s více než jednou.
Důkaz věta je výjimečně přímočarý.
I když je úplný důkaz větaa bez klonování pro naši diskuzi příliš technický, důkaz o věta v případě, že v daném počítači neplatí žádné další ancilla qubits, je v rámci našeho oboru (ancilla qubits jsou qubits použité pro úplně novou. místo během výpočtu a snadno se používá a spravuje v Q #, viz <xref:microsoft.quantum.techniques.qubits>).
V případě takového počítače s více operačními systémem musí být operace klonování jednotnou maticí. Nezakážeme měření, protože by došlo k poškození stavu, který se snažíme klonovat. Jednotná matice musí mít vlastnost, kterou má $ $ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}, $ $ for any State $ \ket{\psi} $.
Vlastnost linearity matice násobení pak znamená, že pro jakýkoliv druhý stav 2 – 2 \ket{\phi} $,

\begin{align} & U\left [\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right] \ket{0}= \frac{1}{\sqrt{2}} U\ket {\ fí} \ KET{0}+ \frac{1}{\sqrt{2}} U\ket {\ psí} \ KET{0}@no__ t_9_ \\ & \qquad\qquad = \frac{1}{\sqrt{2}} \left (\ket{\phi}\ket{\phi} + \ket{\psi}\ket{\psi}\right)\\\\ & \qquad\qquad\ne \left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \ Right) \right) \otimes\left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right).
\end{align}

To poskytuje základní Intuition za věta bez klonování: každé zařízení, které kopíruje neznámý stav, musí způsobit chyby alespoň u některých stavů, které kopíruje.  I když klíč předpokládá, že Cloner funguje lineárně na vstupním stavu, může být porušená přidáním ancilla a měřením ancilla qubits. Tyto interakce také zakládají informace o systému prostřednictvím statistik měření a zabraňují přesné klonování v takových případech také.  Další [informace](xref:microsoft.quantum.more-information)o tom, jak se věta bez klonování, najdete v tématu.

Věta bez klonování je důležité pro kvalitativní porozumění výpočetním procesorům, protože pokud byste mohli naklonovat stavy nenákladných stavových procesorů, pak by vám byla udělena téměř Magical možnost učit se ze států.  Ve skutečnosti byste mohli narušit zásadu nejistoty Heisenberg vaunted.  Alternativně můžete použít optimální Cloner k získání jedné ukázky ze složitosti distribuce nečinnosti a zjistit všechno, co byste se mohli dozvědět o této distribuci jenom z jedné ukázky.  To by vypadalo jako převrácení mince a pozorování hlav a následného oznámení o tom, že na výsledek má odpovědět "Ah. rozdělení této mince musí být Bernoulliho s $p = 0.512643 \ ldots $!"  Takový příkaz by nebyl sensical, protože jeden z bitových informací (výsledek hlav) jednoduše nemůže poskytnout mnoho informací potřebných ke kódování distribuce bez podstatných předchozích informací.  Podobně bez předchozích informací nemůžeme zcela klonovat stav, protože nemůžeme připravit komplet těchto mincí bez znalosti $p $.

Informace nejsou v výpočetním prostředí bezplatné.  Každá qubit měřená má jedinou bitovou informaci a věta bez klonování ukazuje, že není k dispozici žádné zadní vrátka, které by bylo možné zneužít k získání základních kompromisů mezi informacemi získanými v systému a vyvolaným poruchou.

