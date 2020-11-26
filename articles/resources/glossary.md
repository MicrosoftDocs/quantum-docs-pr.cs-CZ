---
title: terming Description Glosář Description: Glosář běžných podmínek, akcí a objektů používaných při práci.
Autor: bradben MS. Author: v-benbra MS. Date: 9/1/2020 MS. téma: UID článku: Microsoft.. Glosář No-Loc:
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

# <a name="quantum-computing-glossary"></a>Glosář pro výpočetní výkon

## <a name="adjoint"></a>Sousednít

Složitá sdružená [operace](xref:microsoft.quantum.glossary#operation). Pro operace, které implementují operátor s jednou [jednotkou](xref:microsoft.quantum.glossary#unitary-operator) , je sousední osoba inverzní k operaci a je označena symbolem Dagger. Například pokud operace `U` představuje operátor s jednou jednotkou $ $ , pak `Adjoint U` představuje $ u ^ \dagger $ . Další informace najdete v tématu [funktor Application](xref:microsoft.quantum.qsharp.functorapplication#functor-application).

## <a name="ancilla"></a>Ancilla

[Qubit](xref:microsoft.quantum.glossary#qubit) , který slouží jako dočasná paměť pro počítač s procesorem a je přidělený a nepřidělený podle potřeby.  Další informace najdete v tématu [víc qubits](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Stav zvonku

Jedno ze čtyř specifických [entangledch](xref:microsoft.quantum.glossary#entanglement) [stavových stavů](xref:microsoft.quantum.glossary#quantum-state) se dvěma qubitsy. Čtyři stavy jsou definovány $ \ket { \beta _ { IJ } } = ( \mathbb { I } \otimes X ^ iZ ^ j) ( \ket { 00 }  +  \ket { 11 } )/ \sqrt { 2 } $ . Stav zvonku se označuje také jako [dvojice EPR](xref:microsoft.quantum.glossary#epr-pair).

## <a name="bloch-sphere"></a>Koule Bloch

Grafické znázornění[qubitch](xref:microsoft.quantum.glossary#qubit) [stavových](xref:microsoft.quantum.glossary#quantum-state) procesorů jako bodu v trojrozměrné oblasti jednotek. Další informace naleznete v tématu  [vizualizace Qubits a transformace pomocí koule Bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Kompatibilní

[Operace](xref:microsoft.quantum.glossary#operation) nebo [funkce](xref:microsoft.quantum.glossary#function) v [ Q# jazyce](https://github.com/microsoft/qsharp-language/tree/main/Specifications/Language#q-language).
Další informace najdete v tématu [ Q# programy](xref:microsoft.quantum.guide.programs) .

## <a name="clifford-group"></a>Skupina Clifford

Sada operací, které zabírají octants [koule Bloch](xref:microsoft.quantum.glossary#bloch-sphere) a účinek, se projeví u [operátorů Pauli](xref:microsoft.quantum.glossary#pauli-operators). Mezi ně patří operace [ $ X $ ](xref:Microsoft.Quantum.Intrinsic.X), [ $ Y $ ](xref:Microsoft.Quantum.Intrinsic.Y), [ $ Z $ ](xref:Microsoft.Quantum.Intrinsic.Z), [ $ H $ ](xref:Microsoft.Quantum.Intrinsic.H) a [ $ S $ ](xref:Microsoft.Quantum.Intrinsic.S).

## <a name="controlled"></a>Kontrol

[Operace](xref:microsoft.quantum.glossary#operation) s incidentem, která přijímá jednu nebo více [qubits](xref:microsoft.quantum.glossary#qubit) jako EnableRSS pro cílovou operaci. Další informace najdete v tématu [funktor Application](xref:microsoft.quantum.qsharp.functorapplication#functor-application).

## <a name="dirac-notation"></a>Zápis Dirac

Symbolická zkrácený tvar, který zjednodušuje reprezentace [stavových krajů](xref:microsoft.quantum.glossary#quantum-state), označovaných také jako *Bra-KET* Notation.  *Bra* část představuje vektor řádku, například a _1 a $ \bra { } = \begin{bmatrix} { } & { _2 } \end{bmatrix} $ a část *KET* představuje vektor sloupce $ \ket { b } = \begin{bmatrix} b { _1 } \\\\ b { _2 } \end{bmatrix} $ . Další informace najdete v tématu [Dirac Notation](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Eigenvalue

Faktor, kterým je velikost [eigenvector](xref:microsoft.quantum.glossary#eigenvector) dané transformace změněna aplikací transformace.  Pro druhou matrici $ M $ a eigenvector $ v $ , pak $ MV = CV $ , kde $ c $ je eigenvalue a může být komplexním číslem libovolného argumentu. Další informace najdete v tématu [pokročilé koncepty matrice](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="eigenvector"></a>Eigenvector

Vektor, jehož směr je beze změny v dané transformaci a jehož velikost je změněna faktorem odpovídajícím [eigenvaluei](xref:microsoft.quantum.glossary#eigenvalue)vektoru. S ohledem na druhou matrici $ M $ a eigenvalue $ c $ pak $ MV = CV $ , kde $ v $ je eigenvector matice a může být komplexním číslem libovolného argumentu. Další informace najdete v tématu [pokročilé koncepty matrice](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="entanglement"></a>Provázání

Částice, jako je například [qubits](xref:microsoft.quantum.glossary#qubit), mohou být propojeny nebo *entangled* tak, aby se nemohly popsány nezávisle na sobě. Jejich výsledky měření se korelují i v případě, že jsou nekonečně zcela oddělené. Entanglement je zásadní pro [měření](xref:microsoft.quantum.glossary#measurement) [stavu](xref:microsoft.quantum.glossary#quantum-state) qubit.  Další informace najdete v tématu [pokročilé koncepty matrice](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="epr-pair"></a>EPR pár

Jedno ze čtyř specifických entangledch [stavových stavů](xref:microsoft.quantum.glossary#quantum-state) se dvěma [qubitsy](xref:microsoft.quantum.glossary#qubit). Čtyři stavy jsou definovány $ \ket { \beta _ { IJ } } = ( \mathbb { 1 } \otimes X ^ iZ ^ j) ( \ket { 00 }  +  \ket { 11 } )/ \sqrt { 2 } $ . Dvojice EPR je také známá jako [stav zvonku](xref:microsoft.quantum.glossary#bell-state) .

## <a name="evolution"></a>Vývoji

Jak se v průběhu času mění [stav](xref:microsoft.quantum.glossary#quantum-state) u. Další informace najdete v tématu [exponenciální matice](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).

## <a name="function"></a>Funkce
Typ subrutiny v Q# jazyce, který je čistě deterministický. I když jsou funkce používány v rámci algoritmů doby provozu, nemohou působit na [operace](xref:microsoft.quantum.glossary#operation) [qubits](xref:microsoft.quantum.glossary#qubit) nebo volání. Další informace najdete v tématu [ Q# programy](xref:microsoft.quantum.guide.programs) .

## <a name="gate"></a>OTP

Zastaralý termín pro určité vnitřní [operace](xref:microsoft.quantum.glossary#operation)s více procesory na základě konceptu klasických bran. [Okruh](xref:microsoft.quantum.glossary#quantum-circuit-diagram) v police je síť bran na základě podobného konceptu klasických logických okruhů.

## <a name="global-phase"></a>Globální fáze

Pokud jsou dva [stavy](xref:microsoft.quantum.glossary#quantum-state) identické až s násobky komplexního čísla $ e ^ { i \phi } $ , říká se, že se liší až do globální fáze. Na rozdíl od místních fází se globální fáze nedají pozorovat prostřednictvím žádného [měřitelného](xref:microsoft.quantum.glossary#measurement). Další informace najdete v tématu [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard

Operace Hadamard (také označovaná jako Hadamard nebo transformační) funguje na jednom [qubit](xref:microsoft.quantum.glossary#qubit) a umístí ji do sudé [pozice](xref:microsoft.quantum.glossary#superposition) $ \ket { 0 } $ nebo $ \ket { 1, } $ Pokud je qubit zpočátku ve $ \ket { } $ stavu 0. V nástroji Q# Tato operace používá předdefinovanou [`H`](xref:Microsoft.Quantum.Intrinsic.H) operaci.

## <a name="immutable"></a>Neměnné

Proměnná, jejíž hodnota se nedá změnit. Neproměnlivá proměnná v Q# je vytvořena pomocí `let` klíčového slova. Chcete-li deklarovat proměnné, které *lze* změnit, použijte klíčové slovo [mutable](xref:microsoft.quantum.glossary#immutable) k deklaraci a `set` klíčové slovo pro úpravu hodnoty. 

## <a name="measurement"></a>Měření

Manipulace s [qubit](xref:microsoft.quantum.glossary#qubit) (nebo sadou qubits), která vede k výsledku pozorování, v důsledku získání klasického bitu. Další informace najdete v tématu [qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Měnitelné

Proměnná, jejíž hodnota může být po vytvoření změněna. Proměnlivá proměnná v Q# je deklarována pomocí `mutable` klíčového slova a upravena pomocí `set` klíčového slova. Proměnné vytvořené pomocí `let` klíčového slova jsou [neměnné](xref:microsoft.quantum.glossary#immutable) a jejich hodnotu nelze změnit.

## <a name="namespace"></a>Obor názvů

Popisek pro kolekci souvisejících názvů (například [operace](xref:microsoft.quantum.glossary#operation), [funkce](xref:microsoft.quantum.glossary#function)a [uživatelsky definované typy](xref:microsoft.quantum.glossary#user-defined-type)). Například obor názvů [Microsoft.. Preparation](xref:Microsoft.Quantum.Preparation) označí všechny symboly definované ve standardní knihovně, které vám pomůžou s přípravou počátečních stavů.

## <a name="operation"></a>Operace

Základní jednotka výpočtu počtu procesorů Q# . Je zhruba ekvivalentní funkci v jazyce C, C++ nebo Python nebo statickou metodou v jazyce C# nebo Java. Další informace najdete v tématu [ Q# programy](xref:microsoft.quantum.guide.programs).

## <a name="oracle"></a>Oracle

Podprogram, který poskytuje informace závislé na datech pro algoritmus v době běhu. Cílem je obvykle poskytnout [nadmnožinu](xref:microsoft.quantum.glossary#superposition) výstupů odpovídajících vstupům, které jsou umístěny na pozici. Další informace najdete v tématu [Oracle](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Částečná aplikace

Volání [funkce](xref:microsoft.quantum.glossary#function) nebo [operace](xref:microsoft.quantum.glossary#operation) bez všech požadovaných vstupů. Tím se vrátí nový, který lze [volat](xref:microsoft.quantum.glossary#callable) , který potřebuje k zadání chybějících parametrů (označených podtržítkem), aby byl dodán v budoucí aplikaci. Další informace naleznete v [části částečná aplikace](xref:microsoft.quantum.qsharp.partialapplication).

## <a name="pauli-operators"></a>Pauli operátory

Sada 3 2 × 2 maticových matricí, které se označují jako `X` `Y` a `Z` operace. $ $ V sadě je často obsažena i matice identity.  $= \begin{bmatrix} 1 & 0 0 \\\\ & \end{bmatrix} $ , $ X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} $ , $ Y = \begin{bmatrix} 0 & -i \\\\ i & 0 \end{bmatrix} $ , $ Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} $ .   Další informace najdete v tématu [operace s jedním qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Diagram okruhu doby

Metoda, která graficky reprezentuje posloupnost [bran](xref:microsoft.quantum.glossary#gate) pro jednoduché programy pro více, například 

![Diagram ukázkového okruhu](~/media/qpe.png). 

Další informace najdete v tématu [okruhy](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Knihovny pro nestejnou doby

Kolekce [operací](xref:microsoft.quantum.glossary#operation), [funkcí](xref:microsoft.quantum.glossary#function) a [uživatelsky definovaných typů](xref:microsoft.quantum.glossary#user-defined-type) pro vytváření Q# programů. [Standardní knihovna](xref:microsoft.quantum.libraries.standard.intro) je nainstalována ve výchozím nastavení. K dispozici jsou další knihovny, které jsou [knihovnou složení](xref:microsoft.quantum.chemistry.concepts.intro), [Knihovna numerických](xref:microsoft.quantum.numerics.intro) knihoven a [Knihovna strojového učení](xref:microsoft.quantum.machine-learning.concepts.intro).

## <a name="quantum-state"></a>Stav pro stav

Přesný stav izolovaného systému pro plnění, ze kterého lze extrahovat pravděpodobnost [měření](xref:microsoft.quantum.glossary#measurement) . V případě, že se jedná o výpočetní výkon, simulátor používá tyto informace k simulaci, jak qubits reaguje na operace. Další informace najdete v tématu [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit

Základní jednotkou informací, která je obdobou *bitu* v klasickém výpočetním prostředí. Další informace najdete v tématu [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Opakovat až do – úspěšné

Koncept se často používá v algoritmech doby využívání, které se skládají z opakovaného použití výpočtu, dokud není splněna určitá podmínka. Pokud podmínka není splněna, často se vyžaduje oprava před opakováním zadáním další iterace. Další informace najdete v [ Q# uživatelské příručce](xref:microsoft.quantum.guide) .

## <a name="standard-libraries"></a>Standardní knihovny

[Operace](xref:microsoft.quantum.glossary#operation), [funkce](xref:microsoft.quantum.glossary#function) a [uživatelsky definované typy](xref:microsoft.quantum.glossary#user-defined-type) , které jsou nainstalovány spolu s Q# kompilátorem během instalace. Standardní implementace knihovny je nezávislá s ohledem na cílové počítače. Další informace najdete v tématu [standardní knihovny](xref:microsoft.quantum.libraries.standard.intro).

## <a name="superposition"></a>Nadpozice

Koncept v této službě znamená, že [qubit](xref:microsoft.quantum.glossary#qubit) je lineární kombinací dvou stavů, $ \ket { 0 } $ a $ \ket { 1 } $ až do [měření](xref:microsoft.quantum.glossary#measurement).  Další informace najdete v tématu [Principy výpočetního](xref:microsoft.quantum.overview.understanding)prostředí.

## <a name="target-machine"></a>Cílový počítač

Cíl kompilace, který snižuje abstraktní program pro plnění do hardwaru nebo simulace. To obvykle zahrnuje opakované zápisy pro mnoho účelů, včetně nahrazení brány, kódování pro korekci chyb, geometrické rozložení a další. Další informace najdete v tématu [simulátory a hostitelské aplikace](xref:microsoft.quantum.machines).

## <a name="teleportation"></a>Teleportace

Metoda pro opětovné generování dat nebo [stav](xref:microsoft.quantum.glossary#quantum-state)u jednoho [qubit](xref:microsoft.quantum.glossary#qubit) z jednoho místa do druhého bez fyzického přesunu qubit pomocí [entanglement](xref:microsoft.quantum.glossary#entanglement) a [měření](xref:microsoft.quantum.glossary#measurement).  Další informace najdete v tématu [okruhy](xref:microsoft.quantum.concepts.circuits) a příslušné Kata při [Katasech](xref:microsoft.quantum.overview.katas).

## <a name="tuple"></a>Řazené kolekce členů

Kolekce hodnot oddělených čárkou, které fungují jako jediná hodnota. *Typ* řazené kolekce členů je definován typy hodnot, které obsahuje. V Q# , řazené kolekce členů jsou [neměnné](xref:microsoft.quantum.glossary#immutable) a mohou být vnořené, obsahují pole nebo použity v poli. Další informace najdete v tématu [řazené kolekce členů](xref:microsoft.quantum.qsharp.valueliterals#tuple-literals).

## <a name="unitary-operator"></a>Operátor jednotných

Operátor, jehož invertování je rovno jeho [sousedním](xref:microsoft.quantum.glossary#adjoint), tj., $ uu ^ { \dagger } = \id $ .

## <a name="user-defined-type"></a>Uživatelem definovaný typ

Vlastní typ, který může obsahovat jednu nebo více pojmenovaných nebo anonymních položek. Další informace najdete v tématu [deklarace typu] Microsoft. qsharp.. typedeclarations # Type-Declarations.
