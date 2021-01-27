---
title: Algoritmy doby ve Q#
description: Seznamte se se základními výpočetními algoritmy, včetně zesílení amplitud, Fourierova transformace, Draper a Beauregard přidávání a odhadu fází.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.libraries.standard.algorithms
no-loc:
- Q#
- $$v
ms.openlocfilehash: d4d8c35b3196ffb9915c6da06116b3c7dfd0562a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859005"
---
# <a name="quantum-algorithms"></a>Algoritmy doby. #

## <a name="amplitude-amplification"></a>Zvětšování amplitudy ##

*Zesílení amplitud* je jedním z základních nástrojů pro výpočetní výkon. Je to základní nápad, který představuje hledání Grover, odhad amplitud a mnoho hlavních algoritmů strojového učení.  Existuje mnoho variant a Q# poskytujeme obecnou verzi na základě zesílení amplitud oblivious s částečnými odrazy, které umožňují nejširší oblast aplikace.

Centrální nápad na zesílení amplitud je rozšířit pravděpodobnost požadovaného výsledku, ke kterému dochází, provedením posloupnosti odrazů.  Tyto odrazy otočí počáteční stav blíže k požadovanému cílovému stavu, který se často označuje jako označený stav.  Konkrétně platí, že pokud je pravděpodobnost měření počátečního stavu v označeném stavu, je $ \sin ^ 2 (\theta) $ poté, co se použije amplituda amplitud $m $ kolikrát se pravděpodobnost úspěchu stala $ \sin ^ 2 ((2 min + 1) \theta) $.  To znamená, že pokud $ \theta = \ PI/[2 (2n + 1)] $ pro určitou hodnotu $n $ pak amplituda zesílení, dokáže zvýšit pravděpodobnost úspěchu až $100 \\ % $ po $n $ iterace zesílení amplitudy.  Vzhledem k tomu, že $ \theta = \sin ^ {-1} (\sqrt{\Pr (úspěch)}) $) $ to znamená, že počet iterací potřebných k obdržení úspěchu je kvadratickě nižší než očekávané číslo, které je potřeba k nalezení označeného stavu bez deterministického použití náhodného vzorkování.

Každá iterace zesílení amplitudy vyžaduje, aby byly zadány dva operátory reflexe. Konkrétně, pokud $Q $ je iterace zesílení a $P _0 $ je operátor projektoru na počáteční mezeru a $P _1 $ je projektor na označené místo, pak $Q =-(\boldone-2P_0) (\boldone-2P_1) $.  Odvolání, že projektor je Hermitian operátor, který má eigenvalues $ + $1 a $0 $ a jako výsledek $ (\boldone-2P_0) $ je jednotná, protože obsahuje eigenvalues, které jsou kořeny Unity (v tomto případě $ \Pm $1). Jako příklad si představte, že se v případě hledání ve službě Grover má počáteční stav $H ^ {\otimes n} \ket {0} $ a označený stav $ \ket{m} $, $P _0 = H ^ {\otimes n} \ket {0} \bra {0} H ^ {\otimes n} $ a $P _1 = \ket{m}\bra{m} $.  Ve většině aplikací amplitudy zesílení $P _0 $ bude projektor do počátečního stavu, což znamená, že $P _0 = \boldone-2 \ KET {\ psí} \ Bra {\ psí} $ pro nějaký vektor $ \ket{\psi} $; Nicméně pro oblivious amplituda amplication $P _0 $ obvykle se projektuje na mnoho stavových stavů (tj. násobnost $ + $1 eigenvalue $P _0 $ je větší než $1 $).

Logika za zesílením amplitudy následuje přímo z Eigen-dekompozice $Q $.  Konkrétně eigenvectors $Q $, že počáteční stav má nenulovou podporu, se může zobrazit jako lineární $1 kombinace $P eigenvectors _0 $ a $P _1 $.  Konkrétně počáteční stav zesílení amplitudy (za předpokladu, že se jedná o $ + $1 eigenvector z $P _0 $), může být zapsaný jako $ $ \ket{\psi} = \frac{-i}{\sqrt {2} } \left (e ^ {i\theta} \ KET {\ psi_ +} + e ^ {-i\theta} \ KET {\ psi_-} \right), $ $ WHERE $ \ket{\ psi_ \Pm} $ jsou eigenvectors $Q $ with eigenvalues $e ^ {\Pm 2i \ théta} $ a podporují pouze eigenvectors _0 $P _1 $ a $P $. $1  Fakt, že eigenvalues jsou $e ^ {\Pm i \theta} $ znamená, že operátor $Q $ provede otočení v dvojrozměrném prostoru určeném dvěma projektory a počátečním stavem, kde je úhel otočení $2 \ théta $.  To je důvod, proč po $m $ iterace $Q $ pravděpodobnost úspěchu je $ \sin ^ 2 ([2 min + 1] \theta) $.

Další užitečnou vlastností, která se z nich nachází, je, že eigenvalue $ \theta $ přímo souvisí s pravděpodobností, že počáteční stav bude označený (v případě, že $P _0 $ je projektor pouze do počátečního stavu).  Vzhledem k tomu, že eigenphases $Q $ jsou $2 \ théta = 2 \ Sin ^ {-1} (\sqrt{\Pr (úspěch)}) $, pak se vám postupuje podle toho, že pokud použijete odhad fáze pro $Q $, můžeme se dozvědět pravděpodobnost úspěchu při použití v rámci jednotkového řízení.  To je užitečné, protože pro zjištění pravděpodobnosti úspěšnosti, která by jinak vyžadovala, je nutné, aby bylo v případě, že vyžaduje kvadratickou, méně aplikací tohoto postupu

Q# zavádí zesílení amplitud jako specializace zesílení amplitudy oblivious.  Zesílení amplitud oblivious umožňuje získat tento moniker, protože projektor na počáteční eigenspace nemusí být projektor do počátečního stavu.  V tomto smyslu je protokol oblivious do počátečního stavu.  Klíčová aplikace zesílení amplitud oblivious je v některých *lineárních kombinacích* Hamiltonian metod simulace, přičemž je v tom, že počáteční stav není znám, ale je entangled s registrem ancilla v protokolu simulace.  Pokud by byl tento registr ancilla měřen jako pevná hodnota, řekněme $0 $, pak tyto metody simulace aplikují požadovanou jednotnou transformaci na zbývající qubits (označované jako systémový registr).  U všech ostatních výsledků měření se ale povede k selhání.  Zesílení amplitud oblivious umožňuje zvýšit pravděpodobnost úspěchu tohoto měření na $100 \\ % $ pomocí výše uvedeného důvodu.  Navíc běžné zesílení amplitudy odpovídá případu, kde je systémový registr prázdný.  Proto Q# používá zesílení amplitud oblivious jako základní podprogram amplitudy zesílení.

Obecná rutina ( `AmpAmpObliviousByReflectionPhases` ) má dva Registry, které voláme `ancillaRegister` a `systemRegister` . Přijímá také dva Oracle pro nezbytné odrazy. `ReflectionOracle`Funguje pouze v době, `ancillaRegister` kdy v `ObliviousOracle` obou registrech funguje dohromady. Vstup do `ancillaRegister` musí být inicializován na hodnotu-1 eigenstate prvního operátoru reflexe $ \boldone-2P_1 $.

Obvykle Oracle připraví stav v výpočetních intervalech $ \ket{0...0} $. V naší implementaci se `ancillaRegister` skládá z jednoho qubit ( `flagQubit` ), který řídí `stateOracle` a zbytek požadovaného ancillas. Je `stateOracle` použita, pokud `flagQubit` je $ \ket {1} $.

Jeden může také poskytovat Oracle `StateOracle` a `ObliviousOracle` místo odrazů prostřednictvím volání `AmpAmpObliviousByOraclePhases` .

Jak bylo zmíněno, tradiční zesílení amplitud je pouze zvláštní případ těchto rutin, kde `ObliviousOracle` je operátor identity a neexistuje qubits systému (tj. `systemRegister` je prázdný). Pokud chcete získat fáze pro částečné odrazy (například pro hledání Grover), funkce `AmpAmpPhasesStandard` je k dispozici. `DatabaseSearch.qs`Ukázkovou implementaci algoritmu Grover najdete v tématu.

Připravujeme fáze qubit rotace na fáze operátoru reflexe, jak je popsáno v dokumentu [G.H. nízká, I. L. Čuangština](https://arxiv.org/abs/1707.05391). Použité fáze s pevným bodem jsou podrobně popsány v [Yoder, low a Čuangština](https://arxiv.org/abs/1409.3305) spolu s fázemi v [dolních Yoder a Čuangština](https://arxiv.org/abs/1603.03996).

V případě pozadí můžete začít ze [standardního zesílení amplitud](https://arxiv.org/abs/quant-ph/0005055) , přejít na Úvod k [oblivious amplitud](https://arxiv.org/abs/1312.1414) a nakonec vytvořit generalize v [dolních a Čuangština](https://arxiv.org/abs/1610.06546). V rámci této [Dominicy](http://www.dominicberry.org/presentations/Durban.pdf)je k disHamiltonianá prezentace s dobrým přehledem této celé oblasti (stejně jako v souvislosti s simulací).

## <a name="quantum-fourier-transform"></a>Fourierova transformace ##

Fourierova transformace je základní nástroj pro klasický rozbor a je stejně důležitá pro výpočetní prostředky.
Kromě toho efektivita aplikace *Fourierova transformace* (QFT) daleko přebírá, co je možné na klasickém počítači, takže při navrhování algoritmu pro plnění hodnot.

Jako přibližné generalizace QFT zajišťujeme <xref:Microsoft.Quantum.Canon.ApproximateQFT> operaci, která umožňuje další optimalizace vyřazením rotací, které nejsou bezpodmínečně nutné pro požadovanou přesnost algoritmu.
Přibližná QFT vyžaduje operaci otočení dyadic $Z $- <xref:Microsoft.Quantum.Intrinsic.RFrac> a <xref:Microsoft.Quantum.Intrinsic.H> operaci.
Předpokládá se, že vstup a výstup se zakódují do kódování ve formátu big endian---to znamená, že qubit s indexem `0` je kódovaný v binárním (největším) bitu binárního typu celého čísla.
Tím se zarovnává s [KET Notation](xref:microsoft.quantum.concepts.dirac)jako registr tří qubits ve stavu $ \ket {100} $ odpovídá $q _0 $ ve stavu $ \ket {1} $, zatímco $q _1 $ a $q _2 $ jsou ve stavu $ \ket {0} $.
Parametr aproximace $a $ určuje úroveň vyřazení $Z $-rotace, tj. $a \in [0.. n] $.
V tomto případě všechny $Z $-rotace $2 \ pi/2 ^ k $, kde $k > a $, se odeberou z okruhu QFT.
Je známo, že pro $k \ge \ log_2 (n) + \ log_2 (1/\epsilon) + $3. jedna může být vázaná \\ na $ | \operatorname{QFT}-\operatorname{AQFT} \\ | < \epsilon $.
Tady $ \\ | \cdot \\ | $ je norma operátoru, která v tomto případě je druhá odmocnina největší [eigenvalue](xref:microsoft.quantum.concepts.matrix-advanced) z $ (\operatorname{QFT}-\operatorname{AQFT}) (\operatorname{QFT}-\operatorname{AQFT}) ^ \dagger $.

## <a name="arithmetic"></a>Aritmetické ##

Stejně jako aritmetická role hraje centrální roli v klasickém výpočetním prostředí, je také nepostradatelná pro výpočetní výkon.  Algoritmy jako algoritmus pro simulaci Shor, metody simulace a také mnoho algoritmů oracular spoléhají na souvislé aritmetické operace.  Nejvíc přístupů k aritmetickému sestavování po okruhech přidávání  Nejjednodušší přizpůsobování přebírá klasický vstup $b $ a přidává hodnotu do stavového pole s celým číslem $ \ket{a} $.  Matematicky, přidávání (což znamená, že Poznámka $ \operatorname{Add} (b) $ pro klasický vstup $b $) má vlastnost, která

$ $ \operatorname{Add} (b) \ket{a} = \ket{a + b}.
$ $ Tento okruh základního přidaných je více než přidaným objektem pro přidání.
Dá se převést na modul pro vyřízení, který má dva vstupy za sebou přes $ $ \operatorname{Add}\ket{a}\ket{b} = \ket{a}\ket{a + b}, $ $ s použitím $n $ řízených aplikací pro přidávání do formuláře \begin{align} \operatorname{Add} \ket{a} \ket{b} & = \Lambda \_ {a \_ 0} \Left (\operatorname{Add} (1) \Right) \Lambda \_ {a \_ 1} \left (\operatorname{Add} (2) \right) \Lambda \_ {a \_ 2} \left (\operatorname{Add} (4) \right) \cdots \Lambda \_ {a \_ {n-1}} \left (\operatorname{Add} ({{n-1}}) \right) \ket{a}\ket{b} \\ \\ & = \ket{a} \ket{b + a}, \end{align} pro $n $-bit integers $a $ a $b $ a další modulo $2 ^ n $.  Zavolá, že Notation $ \Lambda \_ x (A) $ odkazuje pro jakoukoliv operaci $A $ na kontrolovanou verzi této operace s qubit $x $ as.

Podobně klasická řízená násobení (modulární forma, která je základem pro faktor vytváření Shor), lze provádět pomocí podobné série řízených přídavků: \begin{align} \operatorname{Mult} (a) \ket{x}\ket{b} & = \Lambda \_ {x \_ 0} \Left (\operatorname{Add} (2 ^ 0 a) \Right) \Lambda \_ {a \_ 1} \left (\operatorname{Add} (2 ^ 1a) \right) \Lambda \_ {a \_ 2} \left (\operatorname{Add} (2 ^ 2 a) \right) \cdots \Lambda \_ {x \_ {n-1}} \left (\operatorname{Add} ({2 ^ {n-1}} a) \right) \ket{x}\ket{b} \\ \\ & = \ket{x}\ket{b + AX}.
\end{align} je Subtlety s násobnou částí na počítačích, které si můžete všimnout od definice $ \operatorname{Mult} $ výše.  Na rozdíl od přípravné verze tohoto okruhu ukládá produkt ze vstupů v doplňkovém registru, nikoli v vstupním registru.  V tomto příkladu se registr inicializuje s hodnotou $b $, ale obvykle se začne držet hodnota nula.  To je potřeba v důsledku toho, že obecně není multiplikativní INVERT pro obecné $a $ a $x $.  Vzhledem k tomu, že všechny provozní operace, šetří měření, potřebujeme, abychom měli dostatek informací, aby bylo možné Invertovat násobení.  Z tohoto důvodu je výsledek uložen v samostatném poli.  Tento způsob uložení výstupu nevratné operace, jako je násobení, se v samostatném registru označuje jako "Bennett štych" po Charlie Bennett a je základním nástrojem v vratném i nem výpočetním prostředí.

Mnoho okruhů za sebou bylo navrženo pro přidání a každý prozkoumat různé kompromisy na základě počtu qubits (místa) a počtu potřebných operací s bránou (čas).  Prověříme dva vysoce dostupné efektivní přidávání, které je známé jako Draper přidávání a přidávání Beauregard.

### <a name="draper-adder"></a>Přidávání Draper ###

Přidávání Draper je pravděpodobně jedním z nejpokročilejších přidaných kódů, protože přímo vyvolá vlastnosti pro každý z nich k provedení sčítání.  Vhledem k přidávání Draper je, že transformační transformaci lze použít k posunutí fází posunu do bitového posunu.  Následně se postupuje pomocí Fourierova transformace, použití vhodných fází posunu a následnou transformací Fourierova transformace, kterou můžete použít k implementaci přidávání.  Na rozdíl od mnoha dalších přidaných přidaných, Draper přidávání explicitně používá efekty s velkým množstvím, které byly zavedeny prostřednictvím Fourierova transformace.  Nemá přirozený klasický protějšek.  Konkrétní kroky přidávání Draper jsou uvedené níže.

Předpokládejme, že máte dva $n $-bit qubit Registry ukládají celá čísla $a $ a $b $ then pro všechny $a $ $ $ \operatorname{QFT}\ket{a} = \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} e ^ {i2\pi (AJ)/2 ^ n} \ket{j}.
$ $ Pokud definujeme $ $ \ket{\phi \_ k (a)} = \frac {1} {\sqrt {2} } \left (\ket {0} + e ^ {i2\pi a/2 ^ k} \ket {1} \right), $ $ then za některými algebraickýy, uvidíte, že $ $ \operatorname{QFT}\ket{a} = \ket{\phi \_ 1 (a)} \otimes \cdots \otimes \ket{\phi \_ n (a)}.
$ $ Cesta k provedení operace přidávání se pak po zjištění, že součet vstupních hodnot může zapsat jako $ $ \ket{a + b} = \operatorname{QFT} ^ {-1} \ket{\phi \_ 1 (a + b)} \otimes \cdots \otimes \ket{\phi \_ n (a + b)}.
$ $ Celá čísla $b $ a $a $ je pak možné přidat při řízeném otočení fáze na každé qubits v rozloženém formátu pomocí ovládacích prvků $b $ as.

Toto rozšíření může být dále zjednodušené. zaznamená si, že pro libovolné celé číslo $j $ a reálné číslo $x $, $e ^ {i2\pi (x + j)} = e ^ {i2\pi x} $.  Důvodem je to, že Pokud otočíte v kruhu $360 ^ {\circ} $ Degrees ($ 2 \ PI $ radiánů), budete mít přesně na začátku místo, kde jste začali.  Jedinou důležitou součástí $x $ for $e ^ {i2\pi x} $ je proto desetinná část $x $.  Konkrétně, pokud máme binární rozšíření formuláře $x = y +0. x \_ 0x \_ 2 \ ldots x \_ n $ then $e ^ {i2\pi x} = e ^ {i2\pi (0. x \_ 0x \_ 2 \ ldots x \_ {n-1})} $ a proto $ $ \ket{\phi \_ k (a + b)} = \frac {1} {\sqrt {2} } \left (\ket {0} + e ^ {i2\pi [a/2 ^ k +0. b \_ K\ldots b \_ 1]} \ket {1} \right). $ $ to znamená, že pokud provedeme přidání zvýšením každého faktoru tensor v rozšíření fourierova transformace $ \ket{a} $, pak se počet otočení zmenší, protože $k $ klesá.  Tím se podstatně sníží počet bran, které jsou potřeba při přidávání.  Všimněte si kroků Fourierova transformace, fáze sčítání a inverzní funkce pro transformaci Fourierova transformace, které tvoří Draper jako $ \operatorname{QFT} ^ {-1} \left (\phi \\ \! \operatorname{Add}\right) \operatorname{QFT} $. Okruh nároků, který používá toto zjednodušení k implementaci celého procesu, je možné zobrazit níže.

![Zobrazení Draper jako diagram obvodu](~/media/draper.svg)

Každá řízená $eá brána ^ {I2 \ pi/k} $ v okruhu odkazuje na bránu řízených fází.  Taková omezení mají vlastnost, která se nachází na páru qubits, na které jednají, $ \ket {00} \mapsto \ket {00} $, ale $ \ket {11} \mapsto e ^ {I2 \ pi/k} \ KET {11} $.  Tento okruh vám umožní doplněním bez dalších qubits kromě těch, které jsou potřeba k uložení vstupů a výstupů.

### <a name="beauregard-adder"></a>Přidávání Beauregard ###

Přidávání Beauregard je modulární přizpůsobování, které používá přidávání Draper, aby se daly přidat modulo $N $ pro libovolnou hodnotu kladné celé číslo $N $.  Význam modulárních přidaných modulů, jako je například přidání Beauregard, je ve velkém rozsahu od jejich použití v modulárním umocněném kroku v rámci Shor algoritmu pro účely faktoringu.  Modulární přihlašování do modulárního příprocesoru má následující akci pro vstupy a výstupy na $a \ket{b} $, kde $a $ a $b $ jsou přislíbené jako celá čísla $N $, což znamená, že jsou v intervalu $ [0, \ldots, N-1] $.

$ $ \ket{b}\rightarrow \ket{b + a \Text{mod} N} = \begin{Cases} \ket{b + a}, & b + < N \\ \\ \ket{b + a-N} & (b + a) \ge n \end{Cases}.
$$

\\ \! K přidání $a $ a $b $ ve fázi používá modul pro přidávání Beauregard nebo speciálně Draper $ \phi \operatorname{Add} $.  Pak používá stejnou operaci k určení, zda $a + b <N $ pomocí odečítání $N $ a testování, pokud $a + b-N<$0.  Okruh tyto informace uchovává v doplňkovém qubit a potom přidá $N $ back-Register, pokud $a + b<N $.  Pak ukončí nevýpočetní Tento doplňkový bit (Tento krok je nutný, aby bylo zajištěno, že ancilla lze po volání přidávání zrušit přidělení).  Okruh pro přidání Beauregard je uveden níže.

![Zobrazení Beauregard jako diagram obvodu](~/media/beau.svg)

V takovém případě brána $ \phi \\ \! \operatorname{Add} $ má stejný tvar jako $ \phi \\ \! \operatorname{Add} $ s tím rozdílem, že v tomto kontextu je vstup klasický, ale nejedná se o něj.  To umožňuje nahradit řízené fáze v $ \phi \\ \! \operatorname{Add} $ fázemi, které se pak dají kompilovat do menšího počtu operací, aby se snížil počet qubits a počet bran potřebných pro přidání.

Další podrobnosti najdete v tématu [M. Roetteler, Th. Beth](http://doi.org/10.1007/s00200-008-0072-2 ) a [D. Coppersmith](https://arxiv.org/abs/quant-ph/0201067).

### <a name="quantum-phase-estimation"></a>Odhad kvantové fáze ###

Jednou obzvláště důležitou aplikací pro Fourierova transformaci je naučit se eigenvaluesí jednotlivých operátorů, problém známý jako *odhad fáze*.
Vezměte v úvahu jednotkové $U $ a State $ \ket{\phi} $, což znamená, že $ \ket{\phi} $ je eigenstate $U $ s neznámým eigenvalue $ \phi $, \begin{Equation} U\ket {\ fí} = \phi\ket{\phi}.
\end{Equation} Pokud máme přístup pouze k $U $ jako Oracle, můžeme se naučit fázi $ \phi $ pomocí toho, že $Z $ rotace aplikovaná na cíl kontrolované operace se rozšíří zpátky na ovládací prvek.

Předpokládejme, že $V $ je řízená aplikace $U $, jako je \begin{align} V (\ket {0} \otimes \ket{\phi}) & = \ket {0} \otimes \ket{\phi} \textrm{ \\ \\ a} V (\ket {1} \otimes \ket{\phi}) & = e ^ {i \phi} {1} \ket \otimes \ket{\phi}.
\end{Align} a potom lineární, \begin{align} V (\ket{+} \otimes \ket{\phi}) & = \frac{(\ket {0} \otimes \ket{\phi}) + e ^ {i \phi} (\ket {1} \otimes \ket{\phi})} {\sqrt {2} }.
\end{align} můžeme shromažďovat výrazy, abychom zjistili, že \begin{align} V (\ket{+} \otimes \ket{\phi}) & = \frac{\ket {0} + e ^ {i \phi} \ket {1} } {\sqrt {2} } \otimes \ket{\phi} \\ \\ & = (R_1 (\phi) \ket{+}) \otimes \ket{\phi}, \end{align}, kde $R _1 $ je jednotně uplatňovaná <xref:Microsoft.Quantum.Intrinsic.R1> operace.
Nefunguje jinak, účinek použití $V $ je přesně stejný jako při použití $R _1 $ s neznámým úhlem, i když máme přístup pouze k $V $ jako Oracle.
Proto se pro zbytek této diskuze podíváme na fázi odhadu v souvislosti s $R _1 (\phi) $, kterou implementujeme pomocí *Kickback fáze* s názvem.

Vzhledem k tomu, že registr řízení a cíle zůstane untangled po tomto procesu, můžeme použít $ \ket{\phi} $ jako cíl kontrolované aplikace $U ^ $2 a připravit druhý qubit ovládacího prvku ve stavu $R _1 (2 \phi) \ket{+} $.
V tomto případě můžeme získat registraci formuláře \begin{align} \ket{\psi} & = \ sum_ {j = 0} ^ n R_1 (2 ^ j \phi) \ket{+} \\ \\ & \propto \ bigotimes_ {j = 0} ^ {n} \left (\ket {0} + \exp (i 2 ^ {j} \phi) \ket {1} \right) \\ \\ & \propto \ sum_ {k = 0} ^ {2 ^ n-1} \exp (i \phi k) \ket{k} \end{align}, kde $n $ je počet bitů s přesností, které vyžadujeme. a tam, kde jsme použili $ {} \propto {} $ k označení toho, že jsme potlačili faktor normalizace $1/\sqrt{2 ^ n} $.

Pokud předpokládáme, že $ \phi = 2 \pi p/2 ^ k $ pro celé číslo $p $, rozpoznáme to jako $ \ket{\psi} = \operatorname{QFT} \ket{p_0 p_1 \dots p_n} $, kde $p _J $ je $j ^ {\textrm{th}} $ bit of $2 \pi \phi $.
Když použijete sousedící transformaci Fourierova transformace, získáme proto binární reprezentace fáze kódované jako stav pro stav.

V systému Q# je tato operace implementována <xref:Microsoft.Quantum.Characterization.QuantumPhaseEstimation> operací, která přebírá <xref:Microsoft.Quantum.Oracles.DiscreteOracle> implementaci aplikace $U ^ m $ jako funkci kladových celých čísel $m $.
