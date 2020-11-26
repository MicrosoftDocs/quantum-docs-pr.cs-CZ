---
title (název): qubit ve výpočetním prostředí Description: Přečtěte si o qubits, základní informace o výpočetním prostředí.
Autor: QuantumWriter UID: Microsoft.. koncepty. qubit MS. Author: v-benbra MS. Date: 12/11/2017 MS. téma: No-Loc:
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
# <a name="the-qubit"></a>Qubit

Stejně jako bity jsou základními informacemi v klasickém výpočetním prostředí ( [*qubits*](https://en.wikipedia.org/wiki/Qubit) ) jsou základními informacemi v oblasti výpočetní služby.  Pro pochopení tohoto způsobu korespondence se podívejme na Nejjednodušší příklad: jeden qubit.

## <a name="representing-a-qubit"></a>Reprezentace qubit

V případě, že bitová nebo binární číslice může mít hodnotu $ 0 $ nebo $ 1 $ , může qubit mít hodnotu, která je buď z těchto hodnot, nebo je nadmnožinou hodnoty $ 0 $ a $ 1 $ .

Stav jednoho qubit lze popsat pomocí dvojrozměrného vektoru sloupce měrné jednotky. to znamená, že velikost čtverce jeho položek musí být navýšená na $ 1 $ . Tento vektor, označovaný jako vektor stavu, obsahuje všechny informace potřebné k popisu qubit systému, stejně jako jeden bit obsahuje všechny informace potřebné k popisu stavu binární proměnné.

Libovolný dvourozměrný vektor sloupce reálných nebo komplexních čísel s normou $ 1 $ představuje možný stav, který uchovává qubit. Proto $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ představuje stav qubit, pokud $ \alpha $ a $ \beta $ jsou komplexní čísla splňující $ | \alpha | ^ 2 + | \beta | ^ 2 = 1 $ .   Některé příklady platných vektorů stavu, které představují qubits include

$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} , \begin{bmatrix} \frac { 1 } { \sqrt { 2 } } \\\\ \frac { 1 } { \sqrt { 2 } } \end{bmatrix} , \begin{bmatrix} \frac { 1 } { \sqrt { 2 } } \\\\ \frac { – 1 } { \sqrt { 2 } } \end{bmatrix} \text { a } \begin{bmatrix} \frac { 1 } { \sqrt { 2 } } \\\\ \frac { i } { \sqrt { 2 } } \end{bmatrix} .      $$

Vektory stavových stavů $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ a $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ mají zvláštní roli. Tyto dva vektory tvoří základ pro vektorový prostor, který popisuje stav qubit. To znamená, že každý objekt pro každý stav se může zapsat jako součet těchto základních vektorů. Konkrétně je možné, že vektor $ \begin{bmatrix} x \\\\ y \end{bmatrix} $ se zapisuje jako $ x \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} + y \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ . I když by jakékoli rotace těchto vektorů sloužily jako naprosto platnému základu pro qubit, rozhodli jsme se pro ni toto oprávnění, a to voláním *výpočetního základu*.

Tyto dva stavy dobereme, aby odpovídaly dvěma stavům klasického bitu, konkrétně $ 0 $ a $ 1 $ . Standardní konvence je výběr

$$0 \equiv \begin{bmatrix} 1 \\\\ \end{bmatrix} , \qquad 1 0, 1 \equiv \begin{bmatrix} \\\\ \end{bmatrix} ,$$

i když opačná volba by mohla být zároveň zavedená. Proto z nekonečného počtu možných qubitch stavových procesorů, pouze dva odpovídají stavům klasických bitů; všechny ostatní stavy neexistují.

## <a name="measuring-a-qubit"></a>Měření qubit

Teď, když víme, jak vyjádřit qubit, můžeme získat některé Intuition pro to, co tyto stavy reprezentují, a to tak, že se podíváme na koncept [*měření*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics). Měření odpovídá neformálnímu designu "hledání" na qubit, který okamžitě sbalí stav na jeden ze dvou klasických stavů $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ nebo $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ . Když $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ je měřeno qubit, získá výsledek $ 0 $ s pravděpodobností $ | \alpha | ^ 2 $ a výsledek $ 1 $ s pravděpodobností $ | \beta | ^ 2 $ .   Na výsledku $ 0 $ je nový stav qubit $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ ; ve výsledku $ 1 $ jeho stav je $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ . Všimněte si, že tyto pravděpodobnosti se sčítají až o $ 1, $ protože podmínka normalizace $ | \alpha | ^ 2 + | \beta | ^ 2 = 1 $ .

Vlastnosti měření také znamenají, že celkové znaménko vektoru stavu se nevýznamně nepoužívá. Negace vektoru je ekvivalentem $ \alpha \right šipky \alpha $ a $ \beta \right šipky \beta $ . Vzhledem k tomu, že pravděpodobnost měření $ 0 $ a $ 1 $ závisí na velikosti na čtverci podmínek, vkládání těchto značek nemění pravděpodobnost všech. Tyto fáze se často nazývají [ `` *globální fáze*](https://en.wikipedia.org/wiki/Phase_factor) a obecně můžou mít formu $ e ^ { i místo toho, aby se \phi } $ $ \Pm 1 $ .

Poslední důležitou vlastností měření je, že neznamená poškození všech vektorů stavu. Pokud Začínáme s qubit ve stavu $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ , který odpovídá klasickému stavu $ 0 $ , měření tohoto stavu bude vždycky vracet výsledek $ 0 $ a nechat stav nezměněný. V tomto smyslu, pokud máme jenom klasické bity (tj. qubits, které jsou buď $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ nebo $ \begin{bmatrix} 0 \\\\ 1), \end{bmatrix} $ měření neškodí systém. To znamená, že můžeme replikovat klasická data a manipulovat s nimi na počítači se systémem na více počítačů, a to stejně jako na klasický počítač. Schopnost ukládat informace v obou stavech najednou je to, co zvyšuje množství procesorů nad rámec toho, co je možné v klasickém prostředí, a další robsí počítačů s možností kopírování dat do nerozlišené oblasti. Další informace najdete také [v větau No-klonování](https://en.wikipedia.org/wiki/No-cloning_theorem).

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>Vizualizace Qubits a transformací pomocí koule Bloch

Qubits může také obsahovat $ 3 $ D pomocí reprezentace [*koule Bloch*](https://en.wikipedia.org/wiki/Bloch_sphere) .  Koule Bloch poskytuje způsob, jak popsat qubit stav s jednou (což je dvourozměrný komplexní vektor) jako trojrozměrný vektor reálného čísla.  To je důležité, protože nám umožňuje vizualizovat qubit stavy a následně rozvíjet důvod, který může být nevýznamný v porozumění qubitch stavech (kde bohužel Bloch reprezentace sféry).  Koule Bloch se dá vizuálně rozlišit takto:

<!--- ![](.\media\bloch.svg) { Šířka = 50%} --->
![Koule Bloch](~/media/concepts_bloch.png)

Šipky v tomto diagramu ukazují směr, ve kterém je vektor stavu, který ukazuje, a každou transformaci šipky lze představit jako rotaci kolem jedné z OS mohutnosti.
Při zvažování výpočetních hodnot za běhu jako sekvence rotací je to náročné Intuition, ale tento Intuition je obtížné použít k návrhu a popisu algoritmů. Q# Tento problém řeší tím, že poskytuje jazyk popisující taková otočení.

## <a name="single-qubit-operations"></a>Single-Qubit operace

Nastavování počítačů zpracovává data pomocí univerzální sady bran pro plnění, které mohou emulovat jakékoli otočení vektoru stavu.
Tato pojem obecnosti se podobají na pojem univerzální pro tradiční (tj. klasický) výpočet, kde je sada brány považována za univerzální, pokud je možné provést každou transformaci vstupních bitů pomocí omezeného okruhu délky.
Ve výpočetním prostředí jsou platné transformace, které můžeme provádět na qubit, jednotnou transformaci a měření.
*Operace souseda* nebo složitá sdružená transformace má zásadní význam pro náročné na výpočetní výkon, protože je potřeba pro invertování transformací za sebou.

K dispozici jsou pouze čtyři funkce namapované na jeden bit na klasický počítač. Naproti tomu existuje nekonečný počet jednotkových transformací na jednom qubit počítače. Proto žádná konečná sada primitivních operací s názvem, která se označuje jako [*brány*](https://en.wikipedia.org/wiki/Quantum_logic_gate), může přesně replikovat nekonečnou sadu základních transformací, které jsou povolené při práci. To znamená, že na rozdíl od klasického výpočetního prostředí není možné, aby počítač bez nároků implementoval každý možný program na více systémů, a to přesně pomocí omezeného počtu bran. Proto by počítače nemohly být univerzální ve stejném smyslu klasických počítačů. V důsledku toho znamenáme, že sada bran je *univerzální* pro výpočetní výkon, ale ve skutečnosti se jedná o trochu slabší, než je u klasického výpočetního prostředí.
V případě obecnosti vyžadujeme, aby počítač s více podsítěmi v rámci omezené velikosti *používal jenom každou* jednotkovou matici s omezenou délkou.
Jinými slovy, sada bran je univerzální branou, pokud může být jakákoli Jednotková transformace přibližně zapsaná jako produkt z brány z této sady. Vyžadujeme, aby pro všechny předepsané chyby byly brány $ G_ { 1 } G_ { 2 } , \ldots, G_N $ z této sady brány.

$$
G_N G_ { N-1 } \cdots G_2 G_1 \approx U. $$

Vzhledem k tomu, že konvence násobení matice je vynásobit zprava doleva první operace brány v této sekvenci, $ G_N $ je vlastně poslední, který se používá pro vektor stavu. Řekněme, že taková sada brány je univerzální, pokud u každé tolerance chyb $ \epsilon > 0 $ existuje $ G_1, \ldots, G_N $ tak, že vzdálenost mezi $ G_N \ldots G_1 $ a $ U $ je nejvíce $ \epsilon $ . V ideálním případě hodnota $ N $ potřebná k dosažení této vzdálenosti $ \epsilon $ by měla Poly-logarithmically škálovat na $ 1/\ Epsilon $ .

Jak vypadá tato univerzální sada brány jako v praxi?  Nejjednodušší taková univerzální brána pro qubit brány se skládá pouze ze dvou bran: brány Hadamard $ H $ a volání $ T $ -hradlo (označované také jako $ Brána \ PI/8 $ ):

$$
H = \frac { 1 } { \sqrt { 2 1 1 1 } } \begin{bmatrix} & \\\\ & -1 \end{bmatrix} , \qquad T = \begin{bmatrix} 1 & 0 \\\\ 0 & e ^ { i \ PI/4 } \end{bmatrix} .
$$

Z praktických důvodů vztahujících se k opravám chybných stavů ale může být pohodlnější zvážit větší sadu bran, konkrétně jednu, kterou je možné vygenerovat pomocí $ H $ a $ T $ . Pro každou z těchto bran můžeme klasifikovat dvě kategorie: brány Clifford a $ Brána T $ -hradlo.
Toto rozdělení je užitečné, protože v mnoha schématech oprav chyb se říká Clifford, že se pro ně snadno implementují brány, které vyžadují velmi málo prostředků v souvislosti s operacemi a qubits k implementaci odolnosti proti chybám. to znamená, že non-Clifford brány jsou poměrně nákladné při vyžadování odolnosti proti chybám. Standardní sada bran s jedním qubit Clifford, která je [součástí výchozího nastavení v Q# ](xref:microsoft.quantum.libraries.standard.prelude), zahrnuje

$$
H = \frac { 1 } { \sqrt { 2 1 1 1 } } \begin{bmatrix} & \\\\ & -1 \end{bmatrix} , \qquad S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix} = T ^ 2, \qquad X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} = HT ^ 4.,$$

$$
Y = \begin{bmatrix} 0 & – i \\\\ & 0 \end{bmatrix} = t ^ 2HT ^ 4 HT ^ 6, \qquad Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} = T ^ 4.
$$

V tomto případě se operace $ X $ , $ Y $ a $ Z používají $ hlavně často a jsou pojmenované [*Pauli operátory*](https://en.wikipedia.org/wiki/Pauli_matrices) po jejich autorovi Wolfgang Pauli.
Spolu s bránou pro Clifford ( $ $ bránu T-hradlo) se tyto operace dají sestavit tak, aby se v jednom qubitly přibližné měněné transformaci.

Další informace o těchto operacích jejich Bloch a implementacich sféry najdete Q# v tématu [vnitřní operace a funkce](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions).

Jako příklad, jak lze z těchto primitivních typů sestavovat jednotnou transformaci, odpovídají tři transformace, které jsou znázorněné v Blochch oblastech, do sekvence brány $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \mapsto HZH \begin{bmatrix} 1 \\\\ 0 0 \end{bmatrix} = \begin{bmatrix} \\\\ 1 \end{bmatrix} $ .

Zatímco předchozí představuje nejoblíbenější primitivní brány pro popis operací na logické úrovni zásobníku (představit na logické úrovni jako úroveň algoritmu nečinnosti), je často vhodné zvážit méně základních operací na úrovni algoritmu, například operace blíž k úrovni popisu funkce. Naštěstí Q# také obsahuje metody, které jsou k dispozici pro implementaci unitaries na vyšší úrovni, což umožňuje implementovat algoritmy vysoké úrovně bez explicitního rozložení všeho na Clifford a $ T $ -brány.

Nejjednodušší taková primitivní jednoduchá rotace je qubit. Obvykle se berou v úvahu tři rotace s jedním qubit: $ R_x $ , $ R_y $ a $ R_z $ . Aby bylo možné vizualizovat akci $ R_xů rotace (\theta) $ , například Představte si, že jste natáhli správnou dlaždici podél směru $ $ osy x koule Bloch a natočení vektoru na základě ruky pomocí úhlu $ \ théta/2 $ radiánů. Toto matoucí faktor $ 2 $ vzniká od faktu, že kolmé vektory jsou $ 180 ^ \circy $ při vykreslování na koule Bloch, ale ve skutečnosti jsou $ 90 ^ \circ $ stupňů od jejich měření. Odpovídající jednotkové matrice jsou:

\begin{align *} 
 & R_z (\theta) = e ^ { -i\theta z/2 } = \begin{bmatrix} e ^ { -i \ théta/2 } & 0 \\\\ 0 & e ^ { i \ théta/2 } \end{bmatrix} , \\\\ 
 & R_x (\theta) = e ^ { -i\theta x/2 } = HR_z (\theta) H = \begin{bmatrix} \cos (\ théta/2) & -i\sin (\ théta/2) \\\\ -i\sin (\ théta/2) & \cos (\ théta/2) \end{bmatrix} , \\\\ 
 & R_y (\theta) = e ^ { -i\theta a/2 } = SHR_z (\theta) HS ^ \dagger = \begin{bmatrix} \cos (\ théta/2) & -\sin (\ théta/2) \\\\ \sin (\ théta/2) & \cos \end{bmatrix} \end { (\ théta/2). Zarovnat*}

Stejně jako jakékoli tři rotace je možné kombinovat tak, aby prováděly libovolné otočení ve třech dimenzích, je možné vidět z reprezentace Bloch koule, kterou je možné zapsat do jakékoli jednotkové matice jako sekvence tří otočení. Konkrétně pro každou jednotnou matici $ u existuje,,, $ $ \alpha \beta \gamma a \delta $ to $ u = e ^ { i \alpha } R_x () \beta R_z () \gamma R_x () \delta $ . Proto $ R_z (\theta) $ a $ H $ také tvoří univerzální sadu brány, i když se nejedná o samostatnou sadu, protože $ \theta $ může mít libovolnou hodnotu. Z tohoto důvodu a kvůli aplikacím v simulaci nenáročného kódu jsou takové nepřetržité brány zásadní pro výpočet po sobě náročné na výpočetní výkon, zejména na úrovni návrhu algoritmu. Aby byla zajištěna hardwarová implementace odolná proti chybám, bude nakonec zkompilována do diskrétních sekvencí brány, které tyto rotace důkladně nasadí.
