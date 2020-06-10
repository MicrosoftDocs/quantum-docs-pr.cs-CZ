---
title: Glosář pro výpočetní výkon
description: Glosář běžných podmínek, akcí a objektů používaných při práci.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
no-loc:
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
ms.openlocfilehash: 2a3b1fe480b9886d0c11255bb1b1e01402dce4f7
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630092"
---
# <a name="quantum-computing-glossary"></a>Glosář pro výpočetní výkon

## <a name="adjoint"></a>Sousednít

Složitá sdružená [operace](xref:microsoft.quantum.glossary#operation). Pro operace, které implementují operátor s jednou [jednotkou](xref:microsoft.quantum.glossary#unitary-operator) , je sousední osoba inverzní k operaci a je označena symbolem Dagger. Například pokud operace `U` představuje jednotkový operátor $U $ , pak `Adjoint U` představuje $U ^ \dagger $ . Další informace najdete v tématu [sousednít](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).

## <a name="ancilla"></a>Ancilla

[Qubit](xref:microsoft.quantum.glossary#qubit) , který slouží jako dočasná paměť pro počítač s procesorem a je přidělený a nepřidělený podle potřeby.  Další informace najdete v tématu [víc qubits](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Stav zvonku

Jedno ze čtyř specifických [entangledch](xref:microsoft.quantum.glossary#entanglement) [stavových stavů](xref:microsoft.quantum.glossary#quantum-state) se dvěma qubitsy. Čtyři stavy jsou definovány $ \ket { \ Beta_ {IJ } } = (\Mathbb{I } \Otimes X ^ iZ ^ j) (\ket{00 } + \ket{11 } )/\sqrt{2 } $. Stav zvonku se označuje také jako [dvojice EPR](xref:microsoft.quantum.glossary#epr-pair).

## <a name="bloch-sphere"></a>Koule Bloch

Grafické znázornění[qubitch](xref:microsoft.quantum.glossary#qubit) [stavových](xref:microsoft.quantum.glossary#quantum-state) procesorů jako bodu v trojrozměrné oblasti jednotek. Další informace naleznete v tématu [vizualizace Qubits a transformace pomocí koule Bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Kompatibilní

[Operace](xref:microsoft.quantum.glossary#operation) nebo [funkce](xref:microsoft.quantum.glossary#function) v jazyce Q #. Další informace najdete v tématu [operace a funkce](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="clifford-group"></a>Skupina Clifford

Sada operací, které zabírají octants [koule Bloch](xref:microsoft.quantum.glossary#bloch-sphere) a účinek, se projeví u [operátorů Pauli](xref:microsoft.quantum.glossary#pauli-operators). Patří mezi ně operace [$X $ ](xref:microsoft.quantum.intrinsic.x), [$Y $ ](xref:microsoft.quantum.intrinsic.y), [$Z $ ](xref:microsoft.quantum.intrinsic.z) [ $ $H](xref:microsoft.quantum.intrinsic.h) a [$S $ ](xref:microsoft.quantum.intrinsic.s).

## <a name="controlled"></a>Kontrol

[Operace](xref:microsoft.quantum.glossary#operation) s incidentem, která přijímá jednu nebo více [qubits](xref:microsoft.quantum.glossary#qubit) jako EnableRSS pro cílovou operaci. Další informace najdete v tématu [řízené a sousedící operace](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).

## <a name="dirac-notation"></a>Zápis Dirac

Symbolická zkrácený tvar, který zjednodušuje reprezentace [stavových krajů](xref:microsoft.quantum.glossary#quantum-state), označovaných také jako *Bra-KET* Notation.  *Bra* část představuje vektor řádku, například $ \bra{A } = \begin{ bmatrix } a {_1 } & {_2 } \end{ bmatrix } $ a *KET* část představuje vektor sloupce $ \ket{B } = \begin{ bmatrix } B {_1 } \\ \\ B {_2 } \end{ bmatrix } $. Další informace najdete v tématu [Dirac Notation](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Eigenvalue

Faktor, kterým je velikost [eigenvector](xref:microsoft.quantum.glossary#eigenvector) dané transformace změněna aplikací transformace.  Při zadání čtvercové matice $M $ a eigenvector $v a $ pak $MV = CV $ , kde $c $ je eigenvalue a může být komplexním číslem libovolného argumentu. Další informace najdete v tématu [pokročilé koncepty matrice](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="eigenvector"></a>Eigenvector

Vektor, jehož směr je beze změny v dané transformaci a jehož velikost je změněna faktorem odpovídajícím [eigenvaluei](xref:microsoft.quantum.glossary#eigenvalue)vektoru. Při zadání čtvercové matice $M $ a eigenvalue $c a $ pak $MV = CV $ , kde $v $ je eigenvector matice a může být komplexním číslem libovolného argumentu. Další informace najdete v tématu [pokročilé koncepty matrice](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="entanglement"></a>Provázání

Částice, jako je například [qubits](xref:microsoft.quantum.glossary#qubit), mohou být propojeny nebo *entangled* tak, aby se nemohly popsány nezávisle na sobě. Jejich výsledky měření se korelují i v případě, že jsou nekonečně zcela oddělené. Entanglement je zásadní pro [měření](xref:microsoft.quantum.glossary#measurement) [stavu](xref:microsoft.quantum.glossary#quantum-state) qubit.  Další informace najdete v tématu [pokročilé koncepty matrice](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="epr-pair"></a>EPR pár

Jedno ze čtyř specifických entangledch [stavových stavů](xref:microsoft.quantum.glossary#quantum-state) se dvěma [qubitsy](xref:microsoft.quantum.glossary#qubit). Čtyři stavy jsou definovány $ \ket { \ Beta_ {IJ } } = (\Mathbb{1 } \Otimes X ^ iZ ^ j) (\ket{00 } + \ket{11 } )/\sqrt{2 } $. Dvojice EPR je také známá jako [stav zvonku](xref:microsoft.quantum.glossary#bell-state) .

## <a name="evolution"></a>Vývoji

Jak se v průběhu času mění [stav](xref:microsoft.quantum.glossary#quantum-state) u. Další informace najdete v tématu [exponenciální matice](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).

## <a name="function"></a>Funkce
Typ subrutiny v jazyce Q #, který je čistě klasický (nestránkovaného). I když jsou funkce používány v rámci algoritmů doby provozu, nemohou působit na [operace](xref:microsoft.quantum.glossary#operation) [qubits](xref:microsoft.quantum.glossary#qubit) nebo volání. Další informace najdete v tématu [operace a funkce](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="gate"></a>OTP

Starší verze termínu pro [operaci](xref:microsoft.quantum.glossary#operation)na základě konceptu klasických bran logiky. [Okruh](xref:microsoft.quantum.glossary#quantum-circuit-diagram) doby provozu je síť bran (nebo operací) na základě podobného konceptu klasických logických okruhů.

## <a name="global-phase"></a>Globální fáze

Pokud jsou dva [stavy](xref:microsoft.quantum.glossary#quantum-state) identické až na násobek komplexního čísla $e ^ {i \phi } $, říká se, že se liší až do globální fáze. Na rozdíl od místních fází se globální fáze nedají pozorovat prostřednictvím žádného [měřitelného](xref:microsoft.quantum.glossary#measurement). Další informace najdete v tématu [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard

Operace Hadamard (také označovaná jako Hadamard nebo transformační) funguje na jednom [qubit](xref:microsoft.quantum.glossary#qubit) a umístí ji do sudé [pozice](xref:microsoft.quantum.glossary#superposition) $ \ket{0 } $ nebo $ \ket{1 } $, pokud je qubit zpočátku ve stavu $ \ket{0 } $. V Q # se tato operace používá v rámci předdefinované [`H`](xref:microsoft.quantum.intrinsic.h) operace.

## <a name="immutable"></a>Neměnné

Proměnná, jejíž hodnota se nedá změnit. Neproměnlivá proměnná v Q # se vytvoří pomocí `let` klíčového slova. Chcete-li deklarovat proměnné, které *lze* změnit, použijte klíčové slovo [mutable](xref:microsoft.quantum.glossary#immutable) k deklaraci a `set` klíčové slovo pro úpravu hodnoty. 

## <a name="measurement"></a>Měření

Manipulace s [qubit](xref:microsoft.quantum.glossary#qubit) (nebo sadou qubits), která vede k výsledku pozorování, v důsledku získání klasického bitu. Další informace najdete v tématu [qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Měnitelné

Proměnná, jejíž hodnota může být po vytvoření změněna. Proměnlivá proměnná v Q # je deklarována pomocí `mutable` klíčového slova a upravena pomocí `set` klíčového slova. Proměnné vytvořené pomocí `let` klíčového slova jsou [neměnné](xref:microsoft.quantum.glossary#immutable) a jejich hodnotu nelze změnit.

## <a name="namespace"></a>Obor názvů

Popisek pro kolekci souvisejících názvů (například [operace](xref:microsoft.quantum.glossary#operation), [funkce](xref:microsoft.quantum.glossary#function)a [uživatelsky definované typy](xref:microsoft.quantum.glossary#user-defined-type)). Například obor názvů [Microsoft.. Preparation](xref:microsoft.quantum.preparation) označí všechny symboly definované ve standardní knihovně, které vám pomůžou s přípravou počátečních stavů.

## <a name="operation"></a>Operace

Základní jednotka provádění ve službě Q #. Je zhruba ekvivalentní funkci v jazyce C, C++ nebo Python nebo statickou metodou v jazyce C# nebo Java. Další informace najdete v tématu [operace a funkce](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="operator-application"></a>Aplikace operátora

Provádění operací s více operačními operacemi. To obvykle platí jednotnou matici s aktuálním vektorem stavu.

## <a name="oracle"></a>Oracle

Podprogram, který poskytuje informace závislé na datech pro algoritmus v době běhu. Cílem je obvykle poskytnout [nadmnožinu](xref:microsoft.quantum.glossary#superposition) výstupů odpovídajících vstupům, které jsou umístěny na pozici. Další informace najdete v tématu [Oracle](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Částečná aplikace

Volání [funkce](xref:microsoft.quantum.glossary#function) nebo [operace](xref:microsoft.quantum.glossary#operation) bez všech požadovaných vstupů. Tím se vrátí nový, který lze [volat](xref:microsoft.quantum.glossary#callable) , který potřebuje k zadání chybějících parametrů (označených podtržítkem), aby byl dodán v budoucí aplikaci. Například vzhledem k tomu, že se funkce `MyFunc(x : int, y : int) : int {return x + y;}` dá částečně použít pro novou funkci `let NewFunc = MyFunc(_, 3)` . Novou funkci můžete zavolat později s chybějícím parametrem, `NewFunc(2)` který vrátí hodnotu *5*.  Další informace naleznete v [části částečná aplikace](xref:microsoft.quantum.guide.operationsfunctions#partial-application).

## <a name="pauli-operators"></a>Pauli operátory

Množina tří matic 2 × 2 matice, které se označují `X` jako `Y` a `Z` operace. $V sadě je často obsažena i matice identity $I.  $I = \begin{ bmatrix } 1 & 0 \\ \\ 0 & 1 \end{ bmatrix } $, $X = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } $, $Y = \begin{ bmatrix } 0 &-i \\ \\ i & 0 \end{ bmatrix } $, $Z = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } $.   Další informace najdete v tématu [operace s jedním qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Diagram okruhu doby

Metoda pro grafickou reprezentaci posloupnosti [operací](xref:microsoft.quantum.glossary#operation) (nebo [bran](xref:microsoft.quantum.glossary#gate)) pro jednoduché programy pro práci s poli, například 

![Diagram ukázkového okruhu](~/media/qpe.png). 

Další informace najdete v tématu [okruhy](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Knihovny pro nestejnou doby

Kolekce [operací](xref:microsoft.quantum.glossary#operation), [funkcí](xref:microsoft.quantum.glossary#function) a [uživatelsky definovaných typů](xref:microsoft.quantum.glossary#user-defined-type) pro vytváření programů Q #. [Standardní knihovna](xref:microsoft.quantum.libraries.standard.intro) je nainstalována ve výchozím nastavení. K dispozici jsou další knihovny, které jsou [knihovnou složení](xref:microsoft.quantum.chemistry.concepts.intro), [Knihovna numerických](xref:microsoft.quantum.numerics.intro) knihoven a [Knihovna strojového učení](xref:microsoft.quantum.machine-learning.concepts.intro).

## <a name="quantum-state"></a>Stav pro stav

Přesný stav izolovaného systému pro plnění, ze kterého lze extrahovat pravděpodobnost [měření](xref:microsoft.quantum.glossary#measurement) . V případě, že se jedná o výpočetní výkon, simulátor používá tyto informace k simulaci, jak qubits reaguje na operace. Další informace najdete v tématu [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit

Základní jednotkou informací, která je obdobou *bitu* v klasickém výpočetním prostředí. Další informace najdete v tématu [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Opakovat až do – úspěšné

Algoritmus pro všechna ta, který se probabilistically úspěšně. Po selhání bude rutina opakovat až do úspěchu (nebo bylo dosaženo limitu). Další informace najdete v tématu [opakování do úspěchu (ru)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) .

## <a name="standard-libraries"></a>Standardní knihovny

[Operace](xref:microsoft.quantum.glossary#operation), [funkce](xref:microsoft.quantum.glossary#function) a [uživatelsky definované typy](xref:microsoft.quantum.glossary#user-defined-type) , které jsou nainstalovány spolu s kompilátorem Q # během instalace. Standardní implementace knihovny je nezávislá s ohledem na cílové počítače. Další informace najdete v tématu [standardní knihovny](xref:microsoft.quantum.libraries.standard.intro).

## <a name="superposition"></a>Nadpozice

Koncept v této službě znamená, že [qubit](xref:microsoft.quantum.glossary#qubit) je lineární kombinací dvou stavů $ \ket{0 } $ a $ \ket{1 } $, dokud se [neměří](xref:microsoft.quantum.glossary#measurement).  Další informace najdete v tématu [Principy výpočetního](xref:microsoft.quantum.overview.understanding)prostředí.

## <a name="target-machine"></a>Cílový počítač

Cíl kompilace, který snižuje abstraktní program pro plnění do hardwaru nebo simulace. To obvykle zahrnuje opakované zápisy pro mnoho účelů, včetně nahrazení brány, kódování pro korekci chyb, geometrické rozložení a další. Další informace najdete v tématu [simulátory a hostitelské aplikace](xref:microsoft.quantum.machines).

## <a name="teleportation"></a>Teleportace

Metoda pro opětovné generování dat nebo [stav](xref:microsoft.quantum.glossary#quantum-state)u jednoho [qubit](xref:microsoft.quantum.glossary#qubit) z jednoho místa do druhého bez fyzického přesunu qubit pomocí [entanglement](xref:microsoft.quantum.glossary#entanglement) a [měření](xref:microsoft.quantum.glossary#measurement).  Další informace najdete v tématu [okruhy](xref:microsoft.quantum.concepts.circuits) a příslušné Kata při [Katasech](xref:microsoft.quantum.overview.katas).

## <a name="tuple"></a>Řazené kolekce členů

Kolekce hodnot oddělených čárkou, které fungují jako jediná hodnota. *Typ* řazené kolekce členů je definován typy hodnot, které obsahuje. V Q # jsou řazené kolekce členů [neměnné](xref:microsoft.quantum.glossary#immutable) a mohou být vnořené, obsahují pole nebo použity v poli. Další informace naleznete v tématu [typy řazené kolekce členů](xref:microsoft.quantum.guide.types#tuple-types).

## <a name="unitary-operator"></a>Operátor jednotných

Operátor, jehož invertování je rovno jeho [sousedním](xref:microsoft.quantum.glossary#adjoint), tj. $uu ^ {\dagger } = \id $ .

## <a name="user-defined-type"></a>Uživatelem definovaný typ

Kolekce předdefinovaných nebo dříve definovaných typů, které mohou být označovány jako jedna jednotka. Další informace naleznete v tématu [uživatelsky definované typy](xref:microsoft.quantum.guide.types#user-defined-types).