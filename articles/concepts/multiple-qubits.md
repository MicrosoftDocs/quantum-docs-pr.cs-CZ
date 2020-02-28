---
title: Více qubitů
description: Naučte se provádět operace na dvou nebo více qubits.
author: QuantumWriter
uid: microsoft.quantum.concepts.multiple-qubits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 2fa227c823cd87df9c799c043c699e4ce818b8e3
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907541"
---
# <a name="multiple-qubits"></a>Několik Qubits

I když qubit brány mají některé funkce, které jsou v daném čase k dispozici, například schopnost být ve více než jednom stavu, pokud se všechny z nich dostaly na jedno qubit, pak máme zařízení s výpočetním výkonem, které by dwarfed i Kalkulačka může mít jenom klasický počítač.
Skutečná mocnina výpočetního prostředí se dá zjevně projevit, protože naroste počet qubits.
Tato energie nastane v části, protože dimenze vektorového prostoru u vektorů stavu se postupně roste s počtem qubits.
To znamená, že zatímco jedna qubit může být triviální modelovaná, simulace výpočetního množství 50-qubit by pravděpodobně navýšení limitů stávajících počítačů.
Zvýšení velikosti výpočtu pouze pomocí jednoho dalšího qubit *zdvojnásobí* paměť nutnou k uložení stavu a přibližně *zdvojnásobí* výpočetní čas.
Díky tomuto rychlému zdvojnásobení výpočetního výkonu je počítač s qubitsem, který má poměrně malý počet, mnohem vysoký, co nejefektivnějších počítačů dnes, zítra a dalších pro některé výpočetní úlohy.

Proč máme exponenciální růst pro vektory stavu s využitím?  Naším cílem v této části je zkontrolovat pravidla, která se používají k vytváření qubitch států mimo qubit stavy, a také diskutovat o operacích s bránou, které je potřeba zahrnout do naší sady brány, aby tvořily univerzální počítač s procesorovou řadou qubit.
Tyto nástroje jsou nezbytně nutné pro pochopení sady bran, které se běžně používají v kódu Q #, a také k získání Intuition o tom, proč se při práci s nimi, jako je entanglement nebo rušení, vykreslí mnohem výkonnější, než klasický výpočetní výkon.

## <a name="representing-two-qubits"></a>Reprezentace dvou Qubits
Hlavním rozdílem mezi jedním a dvěma qubit stavy je, že qubit stavy jsou dvojrozměrné místo dvojrozměrného rozměru.
Důvodem je to, že výpočetního základu pro qubit stavy je tvořen tensor produkty jednoho qubit států.  Například máme \begin{align} 00 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}1 \\\\ 0\\\\ 0\\\\ 0 \end{bmatrix}, \qquad 01 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 1\\\\ 0\\\\ 0 \end{bmatrix},\\\\ 10 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}0 \\\\ 0\\\\ 1\\\\ 0 \end{bmatrix}, \qquad 11 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 0\\\\ 0 @no__ t_40_ \\ 1 \end{bmatrix}.\\
\end{align}

Pomocí této konstrukce je snadné zjistit, že obecněji stav $n $ qubits je reprezentovaný vektorem jednotek Dimension $2 ^ n $.  Vektor

$ $ \begin{bmatrix} \ alpha_{00} \\\\ \ alpha_{01} \\\\ \ alpha_{10} \\\\ \ alpha_{11} \end{bmatrix} $ $

představuje stav u 2 qubits, pokud je $ | \ alpha_{00}| ^ 2 + | \ alpha_{01}| ^ 2 + | \ alpha_{10}| ^ 2 + | \ alpha_{11}| ^ 2 = 1 $. Stejně jako u jediného qubits, znamená to, že vektor stavu ve více qubits uchovává všechny informace potřebné k popisu chování systému.

Pokud máme dvě samostatné qubits, jednu ve stavu $ \begin{bmatrix} \Alpha \\\\ \beta \end{bmatrix} $ a druhý qubit ve stavu $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $, bude příslušný stav pro dva qubit

$ $ \begin{bmatrix} \Alpha \\\\ \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} = \begin{bmatrix} \Alpha \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\ \delta \end{bmatrix} \end{bmatrix} = \begin{bmatrix} \alpha\gamma \\\\ \alpha\delta \\\\ \beta\gamma \\\\ \beta\delta \end{bmatrix} , $$

kde operace $ \otimes $ se nazývá tensor produkt (nebo produkt Kronecker) vektory. Všimněte si, že i když můžeme vždy přebírat tensor produkt ze dvou stavů qubit, aby bylo možné vytvořit stav, a ne všechny stavy, které se dají zapsat jako tensor produkt ze dvou stavů s jedním qubit.
Například neexistují žádné stavy $ \psi = \begin{bmatrix} \Alpha \\\\ \beta \end{bmatrix} $ a $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $, aby jejich tensor produkt byl stav 

$ $ \psi\otimes \phi = \begin{bmatrix} 1/\ sqrt{2} \\\\ 0 \\\\ 0 \\\\ 1/\ sqrt{2} \end{bmatrix}. $ $ 

Takový qubit stav, který není možné zapsat jako tensor produkt pro jeden qubit stav, se nazývá "entangled"; Tyto dvě qubits se označují jako [*entangled*](https://en.wikipedia.org/wiki/Quantum_entanglement).  Je volně řečeno, protože stav se nedokáže představit jako tensor produkt pro jeden qubit stavů, informace, že stav je uložený, není omezen na jednu z qubits jednotlivě.  Místo toho jsou informace v korelaci mezi dvěma stavy uloženy místně.  Tato nevýznamová informace je jedním z hlavních rozlišujících funkcí, které výpočetní výkon využívá v klasickém výpočetním prostředí, a je zásadní pro celou řadu protokolů [, včetně počtu](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/teleportation) procesorů a [oprav chyb](xref:microsoft.quantum.libraries.error-correction).

## <a name="measuring-two-qubit-states"></a>Měření qubit stavů ##
Měření dvou qubit stavů je velmi podobné měření s jedním qubit. Měření stavu

$ $ \begin{bmatrix} \ alpha_{00} \\\\ \ alpha_{01} \\\\ \ alpha_{10} \\\\ \ alpha_{11} \end{bmatrix} $ $

vypočítá $0 $ s pravděpodobností $ | \ alpha_{00}| ^ $2, $1 $ s pravděpodobností $ | \ alpha_{01}| ^ $2, $10 $ s pravděpodobností $ | \ alpha_{10}| ^ $2 a $11 $ s pravděpodobností $ | \ alpha_{11}| ^ $2. Proměnné $ \ alpha_{00}, \ alpha_{01}, \ alpha_{10}, $ a $ \ alpha_{11}$ byly záměrně pojmenovány, aby toto připojení bylo jasné. Pokud je výsledkem měření $0 $, pak stav nequbitho systému se sbalí a teď je

$ $0 \equiv \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix}.
$$

Je také možné změřit pouze jeden qubit stát qubit. V případech, kdy měříte pouze jeden z qubits, dopad měření se mírně liší, protože celý stav není sbalen do výpočetního stavu, ale je sbalený pouze do jednoho dílčího systému.  Jinými slovy, v takovém případě měření pouze jednoho qubit sbalí pouze jeden z podsystémů, ale ne všechny.  

Pokud to chcete vidět, zvažte měření prvního qubitu následujícího stavu, který se vytvoří pomocí Hadamard transformaci $H $ na dvou qubits zpočátku nastavené na stav "0": $ $ H ^ {\otimes 2} \left (\begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} \right) = \frac{1}{2}\begin{bmatrix}1 & 1 & 1 & 1 \\\\ 1 &-1 & 1 &-1 \\\\ 1 & 1 &-1 &-1 \\\\ 1 &- 1 &-1 & 1 \end{bmatrix}\begin{bmatrix}1\\\\ 0\\\\ 0\\\\ 0 \ konec {bmatrix} = \frac{1}{2}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \mapsto \begin{Cases}\Text{Outcome} = 0 & \frac{1}{\sqrt{2}} \begin{bmatrix}1\\\\ 1\\\\ 0\\\\ 0 \end{bmatrix}\\\\ \Text{Outcome} = 1 & \frac{1}{\sqrt{2}} \begin{bmatrix}0\\\\ 0\\\\ 1\\\\ 1 \end{bmatrix}\\\\ \end{Cases}.
$ $ Oba výsledky mají 50% pravděpodobnost výskytu.  Výsledek, který je 50% pravděpodobnosti pro obojí, může být vytvořen z faktu, že počáteční vektor stavu po dobu, kdy je vyměněno za vyměněné $0 $ s $1 $ na první qubit, je invariantní.

Matematické pravidlo pro měření prvního nebo druhého qubit je jednoduché.  Pokud zadáváme $e _k $ být $k ^ {\rm th} $ výpočetního vektoru a nechte $S sadu všech $e _k $, tak, aby qubit v dané hodnotě přenesl hodnotu $1 $ pro tuto hodnotu $k $.  Pokud vás například zajímá měření prvního qubitu, $S $ by se znamenalo $e _2 \ equiv $10 a $e _3 \ equiv $11.  Podobně, pokud vás zajímá druhý qubit $S $ by se $e _1 \ equiv $1 a $e _3 \equiv $11.  Pak pravděpodobnost měření zvolené qubity na $1 $ je pro stav Vector $ \psi $

$ $ P (\Text{Outcome} = 1) = \ sum_ {e_k \Text{v sadě} S} \psi ^ \dagger e_k e_k ^ \dagger \psi.
$$

Vzhledem k tomu, že každé měření qubit může vracet pouze $0 $ nebo $1 $, pravděpodobnost měření $0 $ je jednoduše $1-P (\Text{Outcome} = 1) $.  Důvodem je, že pouze pro pravděpodobnost měření $1 $ podáváme jenom vzorec.

Akce, kterou taková měření má ve stavu, může být vyjádřena matematicky jako

$ $ \psi \mapsto \frac{\ sum_ {e_k \Text{v sadě} S} e_k e_k ^ \dagger \psi}{\sqrt{P (\Text{Outcome} = 1)}}.
$$

Čtečka opatrnosti se může starat o to, co se stane, když je pravděpodobnost měření nula.  I když je výsledný stav v tomto případě technicky nedefinovaný, nikdy se na takové případy nemusíte starat, protože pravděpodobnost je nula!


Pokud vezmeme $ \psi $ jako jednotnou výše uvedenou vektorovou a máte zájem o měření prvního qubitu. 

$ $ P (\Text{Measurement prvního qubit} = 1) = (\psi ^ \dagger e_2) (e_2 ^ \dagger \psi) + (\psi ^ \dagger e_3) (e_3 ^ \dagger \psi) = | e_2 ^ \dagger \psi | ^ 2 + | e_3 ^ \dagger \psi | ^ 2.
$$

Všimněte si, že toto je jenom součet dvou pravděpodobností, které by se měly očekávat při měření výsledků $10 $ a $11 $, qubits se měření.
V našem příkladu je tato podmínka vyhodnocena jako

$ $ \frac{1}{4}\left | \begin{bmatrix}0 & 0 & 1 & 0 \ konec {bmatrix} \ Begin {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \right | ^ 2 + \frac{1}{4}\left | \begin{bmatrix}0 & 0 & 0 & 1 \ end {bmatrix} \ Begin {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \right | ^ 2 = \frac{1}{2}.
$$

to přesně odpovídá tomu, co naše Intuition oznamuje, že by měla být pravděpodobnost.  Podobně lze stav zapsat jako

$ $ \frac{\frac{e_2}{2}+ \frac{e_3}{2}} {\sqrt{\frac{1}{2}}} = \frac{1}{\sqrt{2}} \begin{bmatrix} 0\\\\ 0\\\\ 1\\\\ 1 \ konec {bmatrix} $ $

znovu v souladu s našimi Intuition.

## <a name="two-qubit-operations"></a>Operace se dvěma qubit
Stejně jako v případě qubit jsou jakékoli jednotkové transformace platnou operací na qubits. Obecně platí, že jednotná transformace v $n $ qubits je matice $U $ o velikosti $2 ^ n \times 2 ^ n $ (takže funguje na vektorech velikosti $2 ^ n $), jako je $U ^{-1} = U ^ \dagger $. Například brána CNOT (řízená-NOT) je běžně používaná qubit brána a je reprezentována následující jednotkovou maticí:

$ $ \operatorname{CNOT} = \begin{bmatrix} 1 \ 0 \ 0 \ 0 \\\\ 0 \ 1 \ 0 \ 0 \\\\ 0 \ 0 \ 0 \ 1 \\\\ 0 \ 0 \ 1 \ 0 \end{bmatrix} $ $

Pomocí qubitch bran na obou qubits můžeme také vytvořit dvě brány – qubit. Pokud například použijeme brány 

$ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} $ $

a

$ $ \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} $ $

na první a druhý qubits, v uvedeném pořadí, je ekvivalentem použití dvou qubit, které jsou uvedené v tensor produktu: $ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} = \begin{bmatrix} AE \ AF \ to \ BF \\\\ AG \ Ah \ BG \ BH \\\\ CE \ CF \ de \ DF \\\\ \ ch \ DG \ DH \end{bmatrix}. $ $, takže můžeme vytvořit qubité brány tím, že převezmete tensor produkt některých známých bran s jedním qubit. Mezi příklady qubitch bran patří $H \otimes H $, $X \otimes \boldone $ a $X \otimes Z $.

Všimněte si, že i když kterákoli ze dvou bran s jedním qubitm definuje qubit bránu tím, že převezme jejich tensor produkt, nebude tato konverzace pravdivá. Ne všechny qubit brány se dají zapsat jako tensor produkt pro brány s jedním qubit.  Taková brána se nazývá *Entangling* brána. Jedním z příkladů brány Entangling je brána CNOT.

Intuition za řízenou bránou se dá zobecnit na libovolné brány.  Řízená brána obecně je bránou, která funguje jako identita (IE nemá žádnou akci), pokud konkrétní qubit není $1 $.  U qubit s $x označením\_x (U) $ jsme si poznamenali řízená jednotná, řízená v tomto případě.  Příklad: $ \ Lambda_0 (U) e\_{1}\otimes {\psi} = e\_{1}\otimes U {\psi} $ a $ \Lambda\_0 (U) e\_{0}\otimes {\psi} = e\_{0}\otimes{\psi} $, kde $e\_$0 a $e\_$1 jsou výpočetní základní vektory pro jednotlivé qubit, které odpovídají hodnotám $0 $ a $1 $.  Zvažte například následující bránu řízená $Z $, kterou můžeme vyjádřit jako $ $ \Lambda\_0 (Z) = \begin{bmatrix}1 & 0 & 0 & 0\\\\0 & 1 & 0 & 0\\\\0 & 0 & 1 & 0\\\\0 & 0 & 0 &-1 \end{bmatrix} = (\boldone\otimes H) \operatorname{CNOT} (\boldone\otimes H).
$$

Sestavování řízené unitaries efektivním způsobem je hlavní výzvou.  Nejjednodušší způsob, jak to implementovat, je vytvoření databáze řízených verzí základních bran a nahrazení všech základních bran v rámci původní jednotnou operací s kontrolovaným protějškem.  To je často poměrně wasteful a chytřejší Insight se často dá použít k tomu, abyste nahradili jenom pár bran řízenými verzemi, aby se dosáhlo stejného dopadu.  Z tohoto důvodu poskytujeme v našem rozhraní možnost provádět Naive metodu řízení nebo povolit uživateli definovat řízenou verzi, pokud je známá Optimalizovaná verze.

Brány se taky dají řídit pomocí klasických informací.  Klasická řízená mimo bránu je například jenom obvyklou nebránou, ale používá se jenom v případě, že je klasický bit $1 $ na rozdíl od bitu.  V tomto smyslu lze klasicky kontrolované brány představit jako příkaz IF v kódu doby, při kterém je brána použita pouze v jedné větvi kódu.


Stejně jako v případě qubit v případě, že je qubit sada braná na jednom místě, je univerzální sada, pokud by se $4 každá z nich mohla blížit jednotkám brány z této sady na libovolnou přesnost.
Jedním z příkladů univerzální sady brány je Hadamard brána, brána T a brána CNOT. Když vezmete produkty z těchto bran, můžeme v každé z nich zaokrouhlit každou jednotkovou matrici na dvě qubits.

## <a name="many-qubit-systems"></a>Řada qubit systémů
Dodržujeme přesně stejné vzory, které jsme prozkoumali v obou qubit případech a Sestavujte mnoho qubitch stavových procesorů z menších systémů.  Tyto stavy jsou sestavené vytvořením tensor produktů menších států.  Zvažte například kódování bitového řetězce $1011001 $ v počítači s více poli.  Tuto možnost můžeme kódovat jako

$ $1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}.
$$

Nefunkční doby fungují přesně stejným způsobem.  Pokud třeba chcete použít bránu $X $ na první qubit a pak CNOT mezi druhou a třetí qubits, můžeme tuto transformaci vyjádřit jako

\begin{align} & (X \otimes \operatorname{CNOT}_{12}\otimes \boldone\otimes \boldone \otimes \boldone \otimes \boldone) \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\\\\ & \qquad\qquad\equiv 0011001.
\end{align}

V mnoha systémech qubit je často potřeba přidělit a zrušit přidělení qubits, která slouží jako dočasná paměť pro počítač s procesorem.  Takový qubit se nazývá ancilla.  Ve výchozím nastavení předpokládáme, že stav qubit se inicializuje do $e _0 $ při přidělení.  Dále předpokládáme, že se znovu vrátí do $e _0 $ před zrušením přidělení.  Tento předpoklad je důležitý, protože pokud se ancilla qubit přestane entangled s jiným registrem qubit, když se změní na nepřidělený, pak proces zrušení přidělení škodí ancilla.  Z tohoto důvodu vždycky předpokládáme, že taková qubits se před vydáním vrátí do původního stavu.

A konečně i když nové brány, které je potřeba přidat do naší sady brány, aby dosáhly univerzálního výpočetního prostředí pro dva počítače s qubitmi procesory, nemusíte v případě qubitho případu zavádět žádné nové brány.  Brány $H $, $T $ a CNOT tvoří univerzální bránu, která je nastavená na mnoho qubits, protože jakákoli obecná jednotná transformace může být rozdělená na řadu dvou qubit rotací.  Potom můžeme využít teoretickou vyvinutou pro qubit případ a znovu ji použít, když máme spoustu qubits.

I když lineární notace algebraických, kterou jsme doposud používali, se dá použít k popsání qubitch stavů, ale při zvyšování velikosti stavů je stále náročná.  Výsledný vektor sloupce pro délku 7 bitového řetězce, například je $128 $ dimenzí, který je vyjadřuje pomocí notace popsané dříve.  Z tohoto důvodu jsme dál předvedli společný zápis ve výpočetním prostředí, které nám umožňuje stručně popsat tyto vysoce multidimenzionální vektory.
