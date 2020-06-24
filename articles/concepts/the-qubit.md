---
title: Qubit ve výpočetním prostředí
description: Seznamte se s qubits, základní jednotkou informací v výpočetním prostředí.
author: QuantumWriter
uid: microsoft.quantum.concepts.qubit
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
ms.openlocfilehash: 0b768190137aa4effe0fbac9c764dff60ec00e16
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269571"
---
# <a name="the-qubit"></a>Qubit

Stejně jako bity jsou základními informacemi v klasickém výpočetním prostředí ( [*qubits*](https://en.wikipedia.org/wiki/Qubit) ) jsou základními informacemi v oblasti výpočetní služby.  Pro pochopení tohoto způsobu korespondence se podívejme na Nejjednodušší příklad: jeden qubit.

## <a name="representing-a-qubit"></a>Reprezentace qubit

Zatímco bitová nebo binární číslice může mít hodnotu buď $0 $ , nebo $1 $ , qubit může mít hodnotu, která je buď z těchto hodnot, nebo z nadmnožiny na základě doby platnosti $0 $ a $1 $ .

Stav jednoho qubit může být popsán dvourozměrným vektorem sloupce Jednotková norma, tj. Velikost čtverce jeho položek musí být součtem $1 $ . Tento vektor, označovaný jako vektor stavu, obsahuje všechny informace potřebné k popisu qubit systému, stejně jako jeden bit obsahuje všechny informace potřebné k popisu stavu binární proměnné.

Libovolný dvourozměrný vektor sloupce reálných nebo komplexních čísel s normou $1 $ představuje možný stav, který uchovává qubit. Takže $ \begin{ bmatrix } \Alpha \\ \\ \beta \end{ bmatrix } $ představuje stav qubit, pokud jsou $ \Alpha $ a $ \beta $ komplexní čísla splňující $ | \Alpha | ^ 2 + | \beta | ^ 2 = 1 $ . Některé příklady platných vektorů stavu, které představují qubits include

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } , \begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac{1 } {\sqrt{2 } } \end{ bmatrix } , \begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac { -1 } {\sqrt{2 } } \end{ bmatrix } , \Text { a} \begin{\frac{1 bmatrix } } {\sqrt{2} \frac{i } \\ \\ } {\sqrt{2 } } \end{ bmatrix } . $ $

Hodnota "Vector State State" $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ a $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $ proveďte speciální roli. Tyto dva vektory tvoří základ pro vektorový prostor, který popisuje stav qubit. To znamená, že každý objekt pro každý stav se může zapsat jako součet těchto základních vektorů. Konkrétně je možné zapsat vektor $ \begin{ bmatrix } x \\ \\ y \end{ bmatrix } $ jako $x \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } + y \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $. I když by jakékoli rotace těchto vektorů sloužily jako naprosto platnému základu pro qubit, rozhodli jsme se pro ni toto oprávnění, a to voláním *výpočetního základu*.

Tyto dva stavy dobereme, aby odpovídaly dvěma stavům klasického bitu, konkrétně $0 $ a $1 $ . Standardní konvence je výběr

$ $0 \equiv \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \qquad 1 \equiv \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } , $ $

i když opačná volba by mohla být zároveň zavedená. Proto z nekonečného počtu možných qubitch stavových procesorů, pouze dva odpovídají stavům klasických bitů; všechny ostatní stavy neexistují.

## <a name="measuring-a-qubit"></a>Měření qubit

Teď, když víme, jak vyjádřit qubit, můžeme získat některé Intuition pro to, co tyto stavy reprezentují, a to tak, že se podíváme na koncept [*měření*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics). Měření odpovídá neformálnímu designu "hledání" na qubit, který okamžitě sbalí stav u jednoho ze dvou klasických stavů $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ nebo $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $. Když se měří qubit, který je dán příslušnou hodnotu Vector $ \begin{ bmatrix } \Alpha \\ \\ \beta \end{ bmatrix } $, získáme výsledek $0 $ s pravděpodobností $ | \Alpha | ^ 2 $ a výsledek $1 $ s pravděpodobností $ | \beta | ^ 2 $ . Na výsledku $0 $ je nový stav qubit $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $; na výsledku $1 $ jeho stav je $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $. Všimněte si, že tyto pravděpodobnosti se sčítají až $1 $ z důvodu normalizační podmínky $ | \Alpha | ^ 2 + | \beta | ^ 2 = 1 $ .

Vlastnosti měření také znamenají, že celkové znaménko vektoru stavu se nevýznamně nepoužívá. Negace vektoru je ekvivalentem $ \Alpha \rightarrow-\Alpha $ and $ \beta \rightarrow-\beta $ . Vzhledem k tomu, že pravděpodobnost měření $0 $ a $1 $ závisí na velikosti na čtverci podmínek, vložením těchto značek nedojde ke změně pravděpodobností. Tyto fáze se často nazývají [ `` *globální fáze*](https://en.wikipedia.org/wiki/Phase_factor) a obecně můžou mít tvar $e ^ {i \phi } $ místo pouze $ \Pm 1 $ .

Poslední důležitou vlastností měření je, že neznamená poškození všech vektorů stavu. Pokud začínáte s qubit ve stavu $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $, který odpovídá klasickému stavu $0 $ , měření tohoto stavu vždy vrátí výsledek $0 $ a ponechá stav bez změny. Pokud je v tomto smyslu jenom klasický počet bitů (tj. qubits, které jsou buď $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ nebo $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $), pak měření neškodí systém. To znamená, že můžeme replikovat klasická data a manipulovat s nimi na počítači se systémem na více počítačů, a to stejně jako na klasický počítač. Schopnost ukládat informace v obou stavech najednou je to, co zvyšuje množství procesorů nad rámec toho, co je možné v klasickém prostředí, a další robsí počítačů s možností kopírování dat do nerozlišené oblasti. Další informace najdete také [v větau No-klonování](https://en.wikipedia.org/wiki/No-cloning_theorem).

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>Vizualizace Qubits a transformací pomocí koule Bloch

Qubits může být také pokryta v $3 $ D pomocí reprezentace [*koule Bloch*](https://en.wikipedia.org/wiki/Bloch_sphere) .  Koule Bloch poskytuje způsob, jak popsat qubit stav s jednou (což je dvourozměrný komplexní vektor) jako trojrozměrný vektor reálného čísla.  To je důležité, protože nám umožňuje vizualizovat qubit stavy a následně rozvíjet důvod, který může být nevýznamný v porozumění qubitch stavech (kde bohužel Bloch reprezentace sféry).  Koule Bloch se dá vizuálně rozlišit takto:

<!--- ![](.\media\bloch.svg){ width=50% } --->
![Koule Bloch](~/media/concepts_bloch.png)

Šipky v tomto diagramu ukazují směr, ve kterém je vektor stavu, který ukazuje, a každou transformaci šipky lze představit jako rotaci kolem jedné z OS mohutnosti.
Při zvažování výpočetních hodnot za běhu jako sekvence rotací je to náročné Intuition, ale tento Intuition je obtížné použít k návrhu a popisu algoritmů. Q # tento problém vyřeší tím, že poskytuje jazyk pro popis takových otočení.

## <a name="single-qubit-operations"></a>Operace s jedním qubit

Nastavování počítačů zpracovává data pomocí univerzální sady bran pro plnění, které mohou emulovat jakékoli otočení vektoru stavu.
Tato pojem obecnosti se podobají na pojem univerzální pro tradiční (tj. klasický) výpočet, kde je sada brány považována za univerzální, pokud je možné provést každou transformaci vstupních bitů pomocí omezeného okruhu délky.
Ve výpočetním prostředí jsou platné transformace, které můžeme provádět na qubit, jednotnou transformaci a měření.
*Operace souseda* nebo složitá sdružená transformace má zásadní význam pro náročné na výpočetní výkon, protože je potřeba pro invertování transformací za sebou.
Q # odráží to tím, že poskytuje metody pro automatické kompilování sekvencí brány do jejich sousedících, které v mnoha případech uloží programátora z nutnosti ručního nastavování kódu adjoints. Příklad najdete tady:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Adj { // Auto-generate the adjoint of the operation
    H(qubit);
}
```

I když se jedná o triviální příklad (jako <xref:microsoft.quantum.intrinsic.h[!OP.NO-LOC(> ), jedná se o samostatně sousedící objekt), vidíte, jak se to bude nevýznamné pro složitější operace qubit.
Další informace najdete v tématu [operace a funkce](xref:microsoft.quantum.guide.operationsfunctions).

K dispozici jsou pouze čtyři funkce namapované na jeden bit na klasický počítač. Naproti tomu existuje nekonečný počet jednotkových transformací na jednom qubit počítače. Proto žádná konečná sada primitivních operací s názvem, která se označuje jako [*brány*](https://en.wikipedia.org/wiki/Quantum_logic_gate), může přesně replikovat nekonečnou sadu základních transformací, které jsou povolené při práci. To znamená, že na rozdíl od klasického výpočetního prostředí není možné, aby počítač bez nároků implementoval každý možný program na více systémů, a to přesně pomocí omezeného počtu bran. Proto by počítače nemohly být univerzální ve stejném smyslu klasických počítačů. V důsledku toho znamenáme, že sada bran je *univerzální* pro výpočetní výkon, ale ve skutečnosti se jedná o trochu slabší, než je u klasického výpočetního prostředí.
V případě obecnosti vyžadujeme, aby počítač s více podsítěmi v rámci omezené velikosti *používal jenom každou* jednotkovou matici s omezenou délkou.
Jinými slovy, sada bran je univerzální branou, pokud může být jakákoli Jednotková transformace přibližně zapsaná jako produkt z brány z této sady. Vyžadujeme, aby pro všechny předepsané chyby byly brány $G _ {1 } , G_ {2 } , \ldots, G_N $ ze sady brány.

$ $ G_N G_ {N-1 } \cdots G_2 G_1 \Approx U. $ $

Vzhledem k tomu, že konvence násobení matice je vynásobit zprava doleva první operace brány v této sekvenci, $G _N $ je vlastně poslední použitou pro vektor stavu. Řekněme, že taková sada brány je univerzální, pokud pro každou odolnost proti chybám $ \epsilon>0 $ existuje $G _1, \ldots G_N $ tak, že vzdálenost mezi $G _N \ldots G_1 $ a $U $ je nejvíce $ \epsilon $ . V ideálním případě $ musí být hodnota $N potřebná k dosažení této vzdálenosti $ \epsilon, $ Poly-logarithmically s $1/\ Epsilon $ .

Jak vypadá tato univerzální sada brány jako v praxi?  Nejjednodušší taková univerzální brána pro qubit brány se skládá jenom ze dvou bran: bránu Hadamard $H $ a bránu $T-incalled, která se označuje $ taky jako brána $ \ PI/8 $ ):

$ $ H = \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 & 1 \\ \\ 1 &-1 \end{ bmatrix } , \qquad T = \begin{ bmatrix } 1 & 0 \\ \\ 0 & e ^ {i \ PI/4 } \end{ bmatrix } .
$$

Z praktických důvodů vztahujících se k opravám chybných stavů ale může být pohodlnější zvážit větší sadu bran, konkrétně jednu, kterou je možné vygenerovat pomocí $H $ a $T $ .
Pro každou z těchto bran můžeme klasifikovat dvě kategorie: Clifford a brány $T $ .
Toto rozdělení je užitečné, protože v mnoha schématech oprav chyb se říká Clifford, že se pro ně snadno implementují brány, které vyžadují velmi málo prostředků v souvislosti s operacemi a qubits k implementaci odolnosti proti chybám. to znamená, že non-Clifford brány jsou poměrně nákladné při vyžadování odolnosti proti chybám. Standardní sada bran s jedním qubit Clifford, která je ve [výchozím nastavení součástí Q #](xref:microsoft.quantum.libraries.standard.prelude), zahrnuje

$ $ H = \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 & 1 \\ \\ 1 &-1 \end{ bmatrix } , \qquad S = \begin{ bmatrix } 1 & 0 \\ \\ 0 & i \end{ bmatrix } = T ^ 2, \qquad X = \begin{ bmatrix } 0 &1 \\ \\ 1 & 0 \end{ bmatrix } = HT ^ 4, $ $

$ $ Y = \begin{ bmatrix } 0 &-i \\ \\ i & 0 \END{ bmatrix } = T ^ 2HT ^ 4 HT ^ 6, \qquad Z = \begin{ bmatrix } 1&0 \\\\ 0 & -1 \end{ bmatrix } = T ^ 4.
$$

V tomto případě se operace $X $ $Y $ a $Z $ používají hlavně často a jsou pojmenovány jako [*operátory Pauli*](https://en.wikipedia.org/wiki/Pauli_matrices) po jejich autorovi Wolfgang Pauli.
Spolu s bránou Clifford ( $ bránu $T) se tyto operace dají sestavit tak, aby se v jednom qubit přibližné měněné transformaci.

Další informace o těchto operacích, jejich reprezentujes Bloch a implementace Q # najdete v tématu [vnitřní operace a funkce](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions).

Jako příklad, jak lze z těchto primitivních typů sestavovat jednotnou transformaci, odpovídají tři transformace, které jsou znázorněné v Blochch oblastech, do sekvence brány $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \mapsto HZH \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $.

Zatímco předchozí představuje nejoblíbenější primitivní brány pro popis operací na logické úrovni zásobníku (představit na logické úrovni jako úroveň algoritmu nečinnosti), je často vhodné zvážit méně základních operací na úrovni algoritmu, například operace blíž k úrovni popisu funkce. Naštěstí, Q # také obsahuje metody, které jsou k dispozici pro implementaci unitaries na vyšší úrovni, který umožňuje implementovat algoritmy vysoké úrovně bez explicitního rozkládání všeho do Clifford a $T $ -bran.

Nejjednodušší taková primitivní jednoduchá rotace je qubit. Obvykle se berou v úvahu tři rotace s jedním qubit: $R _x $ $R _Y $ a $R _Z $ . Chcete-li vizualizovat akci $R otáčení _x (\theta) $, například Představte si, že jste natáhli správnou dlaždici podél směru $x $ osy Bloch a svůj vektor jste natáhli pomocí úhlu kolem výrazu $ \ théta/2 $ radiánů. Tento faktor odmítnutí $2 $ vzniká od faktu, že kolmé vektory jsou $ po rozkreslení na \circou koule v Bloch, ale ve skutečnosti jsou v podstatě $90 ^ \circ $ stupňů od sebe. Odpovídající jednotkové matrice jsou:

\begin{align *} &R_z (\theta) = e ^ {-i\theta z/2 } = \begin{ bmatrix } e ^ {-i \ théta/2 } & 0 \\\\ 0 & e ^ {i \ théta/2 } \end{ bmatrix } , \\ \\ &R_x (\theta) = e ^ {-i\theta x/2 } = HR_z (\theta) H = \begin{ bmatrix } \cos (\ théta/2) &-i\sin (\ théta/2) \\ \\ -i\sin (\ théta/2) & \cos (\ théta/2) \end{ bmatrix } , \\ \\ &R_y (\theta) = e ^ {-i\theta y/2 } = SHR_z (\theta) HS ^ \dagger = \begin{ bmatrix } \cos (\ théta/2) &-\sin (\ théta/2) \\ \\ \sin (\ théta/2) & \cos (\ théta/2) \end{ bmatrix } . \end{align*}

Stejně jako jakékoli tři rotace je možné kombinovat tak, aby prováděly libovolné otočení ve třech dimenzích, je možné vidět z reprezentace Bloch koule, kterou je možné zapsat do jakékoli jednotkové matice jako sekvence tří otočení. Konkrétně pro každou jednotnou matrici $U $ existuje $ \Alpha, \beta, \gamma, \delta $ tak, že $U = e ^ {i \alpha } R_x (\beta) R_z (\gamma) R_x (\delta) $. Proto $R _z (\theta) $ a $H $ také tvoří univerzální sadu brány, i když se nejedná o diskrétní sadu, protože $ \theta $ může mít libovolnou hodnotu. Z tohoto důvodu a kvůli aplikacím v simulaci nenáročného kódu jsou takové nepřetržité brány zásadní pro výpočet po sobě náročné na výpočetní výkon, zejména na úrovni návrhu algoritmu. Aby byla zajištěna hardwarová implementace odolná proti chybám, bude nakonec zkompilována do diskrétních sekvencí brány, které tyto rotace důkladně nasadí.
