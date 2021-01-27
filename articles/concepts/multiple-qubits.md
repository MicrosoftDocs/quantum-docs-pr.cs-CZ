---
title: více qubits Popis: Naučte se provádět operace na dvou nebo více qubits.
Autor: bradben UID: Microsoft.. koncepty. Multiple-qubits MS. Author: v-benbra MS. Date: 12/11/2017 MS. téma: koncepční No-Loc:
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

# <a name="multiple-qubits"></a>Několik Qubits

I když jedna qubitá zařízení mají některé funkce, které jsou uživatelsky intuitivní, například schopnost být ve více než jednom stavu v daném čase, pokud se všichni máme v počítači s procesorem, který by měl být jedním qubit, pak máme zařízení s výpočetním výkonem, které by dwarfed ani Kalkulačka může obsahovat jenom klasický počítač.
Skutečná mocnina výpočetního prostředí se dá zjevně projevit, protože naroste počet qubits.
Tato energie nastane v části, protože dimenze vektorového prostoru u vektorů stavu se postupně roste s počtem qubits.
To znamená, že zatímco jedna qubit může být triviální modelovaná, simulace výpočetního množství 50-qubit by pravděpodobně navýšení limitů stávajících počítačů.
Zvýšení velikosti výpočtu pouze pomocí jednoho dalšího qubit *zdvojnásobí* paměť nutnou k uložení stavu a přibližně *zdvojnásobí* výpočetní čas.
Díky tomuto rychlému zdvojnásobení výpočetního výkonu je počítač s qubitsem, který má poměrně malý počet, mnohem vysoký, co nejefektivnějších počítačů dnes, zítra a dalších pro některé výpočetní úlohy.

Proč máme exponenciální růst pro vektory stavu s využitím?  Naším cílem v této části je zkontrolovat pravidla, která se používají k vytváření qubitch států mimo qubit stavy, a také diskutovat o operacích s bránou, které je potřeba zahrnout do naší sady brány, aby tvořily univerzální počítač s procesorovou řadou qubit.
Tyto nástroje jsou nezbytně nezbytné pro pochopení sady bran, které jsou běžně používány v Q# kódu, a také k získání Intuition o tom, proč se v případě neúspěchu projeví jako entanglement nebo rušení, což vykreslí výpočetní výkon, než klasický výpočetní prostředí.

## <a name="representing-two-qubits"></a>Reprezentace dvou Qubits
Hlavním rozdílem mezi jedním a dvěma qubit stavy je, že qubit stavy jsou dvojrozměrné místo dvojrozměrného rozměru.
Důvodem je to, že výpočetního základu pro qubit stavy je tvořen tensor produkty jednoho qubit států.  Například máme \begin{align}
00 1 0,1 1 0 0 0 \equiv \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} & = \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} , \qquad 01 1 0 \equiv \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} 0 0,\\\\
10 0 1 – 0 0 0 \equiv \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} & = \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} , \qquad 11 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} 0 0 0 1.
\end{align}

Je snadné vidět, že obecněji stav u $ n- $ qubits je reprezentovaný vektorem jednotky dimenze $ 2 ^ n $ pomocí této konstrukce.  Vektor

$$
\begin{bmatrix}\alpha _{ 00 } 01 \\\\ 10 \alpha_ { } \\\\ \alpha _{ 11 } \\\\ \alpha_ { }  \end{bmatrix}
$$

představuje stav u 2 qubits, pokud je $ | \alpha _{ 00 } | ^ 2 + | \alpha_ { 01 } | ^ 2 + | \alpha _{ 10 } | ^ 2 + | \alpha_ { 11 } | ^ 2 = 1 $ . Stejně jako u jediného qubits, znamená to, že vektor stavu ve více qubits uchovává všechny informace potřebné k popisu chování systému.

Pokud máme dvě samostatné qubits, jednu ve stavu $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ a druhý qubit ve stavu $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ , bude odpovídající dva qubit stav    

$$
\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} 
=\begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\  \delta \end{bmatrix} \end{bmatrix}
= \begin{bmatrix} \alpha\gamma \\\\  \alpha\delta \\\\  \beta\gamma \\\\  \beta\delta \end{bmatrix}, $$

kde se operace $ \otimes $ nazývá tensor produkt (nebo Kronecker produkt) vektorů. Všimněte si, že i když můžeme vždy přebírat tensor produkt ze dvou stavů qubit, aby bylo možné vytvořit stav, a ne všechny stavy, které se dají zapsat jako tensor produkt ze dvou stavů s jedním qubit.
Například neexistují žádné stavy $ \psi = \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ a $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ jejich tensor produkt je stav     

$$\psi\otimes\phi = \begin{bmatrix} 1/ \sqrt { 2 } \\\\ 0 \\\\ 0 \\\\ 1/ \sqrt { 2 } \end{bmatrix} .$$ 

Takový qubit stav, který není možné zapsat jako tensor produkt pro jeden qubit stav, se nazývá "entangled"; Tyto dvě qubits se označují jako [*entangled*](https://en.wikipedia.org/wiki/Quantum_entanglement).  Je volně řečeno, protože stav se nedokáže představit jako tensor produkt pro jeden qubit stavů, informace, že stav je uložený, není omezen na jednu z qubits jednotlivě.  Místo toho jsou informace v korelaci mezi dvěma stavy uloženy místně.  Tato nevýznamová informace je jedním z hlavních rozlišujících funkcí, které výpočetní výkon využívá v klasickém výpočetním prostředí, a je zásadní pro celou řadu protokolů [, včetně počtu](https://github.com/microsoft/Quantum/tree/main/samples/getting-started/teleportation) procesorů a [oprav chyb](xref:microsoft.quantum.libraries.error-correction).

## <a name="measuring-two-qubit-states"></a>Měření Two-Qubit stavů ##
Měření dvou qubit stavů je velmi podobné měření s jedním qubit. Měření stavu

$$
    \begin{bmatrix}
        \alpha_{ 00 } 01 \\\\ \alpha_ { }\\\\ 
        \alpha_{ 10 } 11 \\\\ \alpha_ {}
    \end{bmatrix}
$$

Výsledkem je $ 00 $ s pravděpodobností $ | \alpha _{ 00 } | ^ 2 $ , $ 01 $ s pravděpodobností $ | \alpha_ { 01 } | ^ 2 $ , $ 10 $ s pravděpodobností $ | \alpha _{ 10 } | ^ 2 $ a $ 11 $ s pravděpodobností $ | 11 \alpha_ { } | ^ 2 $ . Proměnné $ \alpha _{ 00 } , \alpha_ { 01 } , \alpha _{ 10 } $ a $ 11 \alpha_ { } $ byly záměrně pojmenovány, aby toto připojení bylo jasné. Pokud je výsledkem měření hodnota 00, znamená to, že $ $ stav 2 – 2 qubit systému se sbalí a teď je

$$
    16.12.00 \equiv
    \begin{bmatrix}
        1 \\\\ 
        0,8 \\\\ 
        0,8 \\\\ 
        0 \end{bmatrix} .
$$

Je také možné změřit pouze jeden qubit stát qubit. V případech, kdy měříte pouze jeden z qubits, dopad měření se mírně liší, protože celý stav není sbalen do výpočetního stavu, ale je sbalený pouze do jednoho dílčího systému.  Jinými slovy, v takovém případě měření pouze jednoho qubit sbalí pouze jeden z podsystémů, ale ne všechny.  

Pokud to chcete vidět, zvažte měření prvního qubitu následujícího stavu, který se vytvoří pomocí Hadamard transformace $ H $ na dvou qubits zpočátku nastavené na stav 0: $$
H ^ { \otimes 2 } \left ( \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \right ) = \frac { 1 } { 2 } \begin{bmatrix} 1 & 1 & 1 1 1 & -1 1- \\\\ & & & 1 \\\\ 1 & 1 & -1 & -1 \\\\ 1 & -1 & -1 1 1 0 0 0 & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} = \frac { 1 } { 2 1 1 1 } \begin{bmatrix} \\\\ \\\\ \\\\ 1 \end{bmatrix} \mapsto \begin{cases} \text { výsledek } = 0 & \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ 1 \\\\ 0 \\\\ 0 \end{bmatrix} \\\\ \text { výsledek } = 1 & \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 0 \\\\ 0 \\\\ \\\\ \end{bmatrix} \\\\ \end{cases} 1  
$$
U obou výsledků je k dispozici 50% pravděpodobnost výskytu.  Výsledek, který je 50% pravděpodobnosti pro obojí, může být od faktu, že počáteční vektor stavu neplatí jako invariantující se zahozením $ 0 $ $ $ a 1 na prvním qubit.

Matematické pravidlo pro měření prvního nebo druhého qubit je jednoduché.  Pokud $ $ přidáváme e_k být $ k ^ { \rm, } $ vektor výpočetního základu a umožníme jim $ $ sadu všech $ e_k $ tak, že qubit v dané hodnotě převezme hodnotu $ 1 $ pro tuto hodnotu $ k $ .  Pokud vás například zajímá měření prvního qubitu, bude se $ $ skládat z $ e_1 \equiv 10 $ a $ e_3 \equiv 11 $ .  Podobně platí, že pokud vás zajímá druhá qubita, budou se $ $ skládat z $ e_2 \equiv 01 $ a $ e_3 \equiv 11 $ .  Pak pravděpodobnost měření zvoleného qubitu na $ $ hodnotu 1 je pro vektor stavu $\psi$

$$
P ( \text { výsledek } = 1) = \sum _ { e_k \text { v sadě } S } \psi ^ \dagger e_k e_k ^ \dagger \psi .
$$

> [!NOTE]
> V tomto dokumentu používáme formát Little-endian k označení výpočetního základu. Ve formátu Little endian se nejdříve najdou nejméně významné bity. Například číslo čtyři ve formátu Little endian je reprezentované řetězcem bitů 001.

Vzhledem k tomu, že každé měření qubit může vracet pouze $ 0 $ nebo $ 1 $ , pravděpodobnost měření $ 0 $ je pouze $ 1 – P ( \text { výsledek } = 1) $ .  To je důvod, proč explicitně dáváme vzorec pro pravděpodobnost měření $ 1 $ .

Akce, kterou taková měření má ve stavu, může být vyjádřena matematicky jako

$$
\psi\mapsto \frac{\sum _ { e_k \text { v sadě } S } e_k e_k ^ \dagger \psi } { \sqrt { P ( \text { výsledek } = 1) } } .
$$

Čtečka opatrnosti se může starat o to, co se stane, když je pravděpodobnost měření nula.  I když je výsledný stav v tomto případě technicky nedefinovaný, nikdy se na takové případy nemusíte starat, protože pravděpodobnost je nula!


Pokud budeme $ \psi $ odpovídat výše uvedenému vektoru stavu a máte zájem o měření prvního qubitu, pak 

$$
P ( \text { měření prvních qubit } = 1) = ( \psi ^ \dagger e_1) (e_1 ^ \dagger \psi ) + ( \psi ^ \dagger e_3) (e_3 ^ \dagger \psi ) = | e_1 ^ \dagger \psi | ^ 2 + | e_3 ^ \dagger \psi | ^ 2.
$$

Všimněte si, že toto je jenom součet dvou pravděpodobností, které by se měly očekávat pro měření výsledků $ 10 a 11, a to všechno, co je $ $ $ qubits měřit.
V našem příkladu je tato podmínka vyhodnocena jako

$$
\frac{1 } { 4 } \left | \begin{bmatrix} 0 & 0 & 1 0 1 1 1 1 & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \right | ^ 2 + \frac { 1 4 0 0 0 1 1 1 1 1 } { } \left | \begin{bmatrix} & & & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \right | ^ 2 = \frac { 1 } { 2 } .
$$

to přesně odpovídá tomu, co naše Intuition oznamuje, že by měla být pravděpodobnost.  Podobně lze stav zapsat jako

$$
\frac{\frac{e_1 } { 2 } + \frac { e_3 } { 2 } } { \sqrt { \frac { 1 } { 2 } } } = \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 0 \\\\ 0 \\\\ 1 \\\\ 1\end{bmatrix}
$$

znovu v souladu s našimi Intuition.

## <a name="two-qubit-operations"></a>Two-Qubit operace
Stejně jako v případě qubit jsou jakékoli jednotkové transformace platnou operací na qubits. Obecně platí, že jednotná transformace na $ n $ qubits je matice $ o $ velikosti $ 2 ^ n \times 2 ^ n $ (takže funguje na vektorech velikosti $ 2 ^ n), což je $ $ u ^ { -1 } = u ^ \dagger $ .
Například brána CNOT (řízená-NOT) je běžně používaná qubit brána a je reprezentována následující jednotkovou maticí:

$$
\operatorname{CNOT } = \begin{bmatrix} 1 \ 0 \ 0 \ 0  \\\\  0 \ 1 \ 0 \ 0 \\\\  0 \ 0 \ 0 \ 1 \\\\  0 \ 0 \ 1 \ 0 \end{bmatrix}
$$

Pomocí qubitch bran na obou qubits můžeme také vytvořit dvě brány – qubit. Pokud například použijeme brány 

$$
\begin{bmatrix}
a \ b \\\\ c \ d \end{bmatrix}
$$

a

$$\begin{bmatrix}
e \ f \\\\ g \ h \end{bmatrix}
$$

na první a druhý qubits, v uvedeném pořadí, je ekvivalentem použití dvou qubit, které jsou uvedené v tensor produktu: $$\begin{bmatrix}
a \ b \\\\ c \ d \end{bmatrix}
\otimes 
\begin{bmatrix}
e \ f \\\\ g \ h \end{bmatrix}=
    \begin{bmatrix}
    AE \ AF \ je \ Bf \\\\
    AG \ Ah \ BG \ BH \\\\
    CE \ CF \ de \ DF \\\\
    \ ch \ DG \ DH \end{bmatrix} .$$
Proto můžeme pořizovat qubité brány tím, že tensor produkt s některými známými branami s jedním qubit. Mezi příklady qubitch bran patří $ h \otimes h $ , $ X \otimes \boldone $ a $ x \otimes Z $ .

Všimněte si, že i když kterákoli ze dvou bran s jedním qubitm definuje qubit bránu tím, že převezme jejich tensor produkt, nebude tato konverzace pravdivá. Ne všechny qubit brány se dají zapsat jako tensor produkt pro brány s jedním qubit.  Taková brána se nazývá *Entangling* brána. Jedním z příkladů brány Entangling je brána CNOT.

Intuition za řízenou bránou se dá zobecnit na libovolné brány.  Řízená brána obecně je bránou, která funguje jako identita (IE nemá žádnou akci), pokud konkrétní qubit není $ 1 $ .  U qubit s označením $ x $ $ \Lambda \_ (U) $ jsme si poznamenali řízená jednotnou a řízenou v tomto případě.  Jako příklad $ \Lambda _0 (u) e \_ { 1 } \otimes { \psi } = e \_ { 1 } \otimes U { \psi } $ a $ \Lambda \_ 0 (u) e \_ { 0 } \otimes { \psi } = e \_ { 0 } \otimes { \psi } $ , kde $ e \_ 0 $ a $ e \_ 1 $ jsou výpočetní základní vektory pro jednu qubit, která odpovídá hodnotám $ 0 $ a $ 1 $ .  Zvažte například následující $ bránu řízená-Z, $ kterou můžeme vyjádřit jako $$
\Lambda\_0 (Z) 1 0 0 0 0 0 0 0 0 0 0 0 0 = \begin{bmatrix} & & & \\\\ & & & \\\\ & & & \\\\ & & & -1 \end{bmatrix} = ( \boldone \otimes h) \operatorname { CNOT } ( \boldone \otimes h).
$$

Sestavování řízené unitaries efektivním způsobem je hlavní výzvou.  Nejjednodušší způsob, jak to implementovat, je vytvoření databáze řízených verzí základních bran a nahrazení všech základních bran v rámci původní jednotnou operací s kontrolovaným protějškem.  To je často poměrně wasteful a chytřejší Insight se často dá použít k tomu, abyste nahradili jenom pár bran řízenými verzemi, aby se dosáhlo stejného dopadu.  Z tohoto důvodu poskytujeme v našem rozhraní možnost provádět Naive metodu řízení nebo povolit uživateli definovat řízenou verzi, pokud je známá Optimalizovaná verze.

Brány se taky dají řídit pomocí klasických informací.  Klasická řízená mimo bránu je například jenom obvyklou nebránou, ale používá se jenom v případě, že je klasický bit $ 1 $ na rozdíl od bitu.  V tomto smyslu lze klasicky kontrolované brány představit jako příkaz IF v kódu doby, při kterém je brána použita pouze v jedné větvi kódu.


Stejně jako v případě qubitho případu je qubit sada brány univerzální, pokud by každá $ 4 \times $ jednotná matice mohla být Přibližná součinem bran z této sady až po libovolnou přesnost.
Jedním z příkladů univerzální sady brány je Hadamard brána, brána T a brána CNOT. Když vezmete produkty z těchto bran, můžeme v každé z nich zaokrouhlit každou jednotkovou matrici na dvě qubits.

## <a name="many-qubit-systems"></a>Many-Qubit systémy
Dodržujeme přesně stejné vzory, které jsme prozkoumali v obou qubit případech a Sestavujte mnoho qubitch stavových procesorů z menších systémů.  Tyto stavy jsou sestavené vytvořením tensor produktů menších států.  Zvažte například kódování bitového řetězce $ 1011001 $ v počítači s více poli.  Tuto možnost můžeme kódovat jako

$$
1011001 0 1 – 0 0 \equiv \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} 1 0 0 0.1.
$$

Nefunkční doby fungují přesně stejným způsobem.  Například pokud chceme použít $ $ bránu X na první qubit a pak provést CNOT mezi druhou a třetí qubits, můžeme tuto transformaci vyjádřit jako

\begin{align}
&(X \otimes \operatorname { CNOT } _ { 12 } \otimes \boldone \otimes \boldone \otimes \boldone \otimes \boldone ) \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} \\\\ 0 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ 0 1 0 0 1\end{bmatrix}\\\\
&\qquad\qquad\equiv 0011001. \end{align}

V mnoha systémech qubit je často potřeba přidělit a uvolnit qubits, která slouží jako dočasná paměť pro počítač s více operačními systémy.  Takový qubit se nazývá ancilla.  Ve výchozím nastavení předpokládáme, že se stav qubit inicializuje na $ e_0 $ při přidělování.  Dále předpokládáme, že se znovu vrátí do $ e_0 $ před zrušením přidělení.  Tento předpoklad je důležitý, protože pokud se ancilla qubit přestane entangled s jiným registrem qubit, když se bude narušit, pak proces navracení dolů škodí ancilla.  Z tohoto důvodu vždycky předpokládáme, že taková qubits se před vydáním vrátí do původního stavu.

A konečně i když nové brány, které je potřeba přidat do naší sady brány, aby dosáhly univerzálního výpočetního prostředí pro dva počítače s qubitmi procesory, nemusíte v případě qubitho případu zavádět žádné nové brány.  Brány $ H $ , $ T $ a CNOT tvoří univerzální bránu, která je nastavená na mnoho qubits, protože každou obecnou jednotnou transformaci lze rozdělit do řady dvou qubit rotací.  Potom můžeme využít teoretickou vyvinutou pro qubit případ a znovu ji použít, když máme spoustu qubits.

I když lineární notace algebraických, kterou jsme doposud používali, se dá použít k popsání qubitch stavů, ale při zvyšování velikosti stavů je stále náročná.  Výsledný vektor sloupce pro délku 7 bitového řetězce, například je $ 128 $ dimenzionální, který je vyjadřuje pomocí notace popsané dříve.  Z tohoto důvodu jsme dál předvedli společný zápis ve výpočetním prostředí, které nám umožňuje stručně popsat tyto vysoce multidimenzionální vektory.
