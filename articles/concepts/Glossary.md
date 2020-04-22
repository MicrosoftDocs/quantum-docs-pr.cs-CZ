---
title: Glosář kvantových výpočtů
description: Glosář běžných pojmů, akcí a objektů používaných v kvantové majetrové práci.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: ee78515a0f47730b7d3df10da0853c5b8a7f6624
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2020
ms.locfileid: "81482233"
---
# <a name="quantum-computing-glossary"></a>Glosář kvantových výpočtů

## <a name="adjoint"></a>Adjoint

Komplexní konjugát transponovat [operace](xref:microsoft.quantum.glossary#operation). Pro operace, které implementují [unitární](xref:microsoft.quantum.glossary#unitary-operator) operátor, adjoint je inverzní operace a je označen symbolem dýky. Například pokud operace `U` představuje unitární operátor $U$, pak `Adjoint U` představuje $U^\dagger$. Další informace naleznete v tématu [Adjoint](xref:microsoft.quantum.language.file-structure#adjoint).

## <a name="ancilla"></a>Ancilla

[Qubit,](xref:microsoft.quantum.glossary#qubit) který slouží jako dočasná paměť pro kvantový počítač a je přidělena a de-přidělena podle potřeby.  Další informace naleznete [v tématu Multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Stav zvonku

Jeden ze čtyř specifických maximálně [zamotaných](xref:microsoft.quantum.glossary#entanglement) [kvantových stavů](xref:microsoft.quantum.glossary#quantum-state) dvou qubitů. Čtyři stavy jsou definovány $\ket{\beta_{ij}} = (\mathbb{I} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$. Bell stát je také známý jako [pár EPR](xref:microsoft.quantum.glossary#epr-pair).

## <a name="bloch-sphere"></a>Blážová koule

Grafické znázornění[jednoqubitového](xref:microsoft.quantum.glossary#qubit) [kvantového stavu](xref:microsoft.quantum.glossary#quantum-state) jako bodu v trojrozměrné jednotkové sféře. Další informace naleznete v [tématu Vizualizace qubitů a transformací pomocí Sféra bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Callable

[Operace](xref:microsoft.quantum.glossary#operation) nebo [funkce](xref:microsoft.quantum.glossary#function) v jazyce Q#. Další informace naleznete v [tématu Operation and function types](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="clifford-group"></a>Cliffordskupina

Soubor operací, které zabírají oktanů [sféry Bloch](xref:microsoft.quantum.glossary#bloch-sphere) a účinek permutace [operátorů Pauli](xref:microsoft.quantum.glossary#pauli-operators). Patří mezi ně operace [$X $](xref:microsoft.quantum.intrinsic.x), [$Y $,](xref:microsoft.quantum.intrinsic.y) [$Z$,](xref:microsoft.quantum.intrinsic.z) [$H$](xref:microsoft.quantum.intrinsic.h) a [$S$.](xref:microsoft.quantum.intrinsic.s)

## <a name="controlled"></a>Kontrolované

Kvantová [operace,](xref:microsoft.quantum.glossary#operation) která bere jeden nebo více [qubitů](xref:microsoft.quantum.glossary#qubit) jako aktivátory pro cílovou operaci. Další informace naleznete v [tématu Controlled](xref:microsoft.quantum.language.type-model#controlled).

## <a name="dirac-notation"></a>Dirac notace

Symbolický zkratka, která zjednodušuje reprezentaci [kvantových stavů](xref:microsoft.quantum.glossary#quantum-state), také volal *podprsenka-ket* notace.  Část *podprsenky* představuje vektor řádku, například $\bra{A} = \begin{bmatrix} A{_1} & A{_2} \end{bmatrix}$ a *část ket* představuje vektor sloupce, $\ket{B} = \begin{bmatrix} B{_1} \\ \\ B{_2} \end{bmatrix}$. Další informace naleznete [v tématu Dirac Notation](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Reálná hodnota

Faktor, kterým se velikost [emitačního vektoru](xref:microsoft.quantum.glossary#eigenvector) dané transformace mění použitím transformace.  Vzhledem k tomu, čtvercová matice $M$ a přívektor $v$, pak $Mv = cv$, kde $c$ je eigenvalue a může být komplexní počet libovolného argumentu. Další informace naleznete v [tématu Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="eigenvector"></a>První vektor

Vektor, jehož směr není změněn danou transformací a jehož velikost se mění koeficientem odpovídajícím [vlastní hodnotě](xref:microsoft.quantum.glossary#eigenvalue)tohoto vektoru . Vzhledem k tomu, čtvercová matice $M$ a emigenvalue $c$, pak $Mv = cv$, kde $v$ je malý vektor matice a může být komplexní počet libovolného argumentu. Další informace naleznete v [tématu Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="entanglement"></a>Zapletení

Kvantové částice, jako jsou [qubity](xref:microsoft.quantum.glossary#qubit), mohou být spojeny nebo *zamotány* tak, že nemohou být popsány nezávisle na sobě. Jejich výsledky měření jsou korelovány, i když jsou odděleny nekonečně daleko. Zapletení je nezbytné pro [měření](xref:microsoft.quantum.glossary#measurement) [stavu](xref:microsoft.quantum.glossary#quantum-state) qubitu.  Další informace naleznete v [tématu Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="epr-pair"></a>Dvojice EPR

Jeden ze čtyř specifických maximálně zamotaných [kvantových stavů](xref:microsoft.quantum.glossary#quantum-state) dvou [qubitů](xref:microsoft.quantum.glossary#qubit). Čtyři stavy jsou definovány $\ket{\beta_{ij}}{1} = (\mathbb \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$. Dvojice EPR je také známá jako [bellský stav](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>Vývoj

Jak se [kvantový stav](xref:microsoft.quantum.glossary#quantum-state) mění v průběhu času. Další informace naleznete [v tématu Matrix exponenciály](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).

## <a name="function"></a>Funkce
Typ podprogramu v jazyce Q#, který je čistě klasický (nekvantový). Zatímco funkce se používají v rámci kvantové algoritmy, nemohou působit na [qubity](xref:microsoft.quantum.glossary#qubit) nebo call [operace](xref:microsoft.quantum.glossary#operation). Další informace naleznete v [tématu Operation and function types](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="gate"></a>Gate

Starší termín pro kvantovou [operaci](xref:microsoft.quantum.glossary#operation), založený na konceptu klasických logických bran. [Kvantový obvod](xref:microsoft.quantum.glossary#quantum-circuit-diagram) je síť bran (nebo operací), založená na podobném konceptu klasických logických obvodů.

## <a name="global-phase"></a>Globální fáze

Pokud jsou dva [stavy](xref:microsoft.quantum.glossary#quantum-state) identické až do násobku komplexního čísla $e^{i\phi}$, říká se, že se liší až do globální fáze. Na rozdíl od místních fází nelze globální fáze pozorovat pomocí [žádného měřitelství](xref:microsoft.quantum.glossary#measurement). Další informace naleznete [v tématu Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard (Hadamard)

Operace Hadamard (označovaná také jako brána Hadamard nebo transformace) působí na jeden [qubit](xref:microsoft.quantum.glossary#qubit) a{0}umístí jej do{1}rovnoměrné [superpozice](xref:microsoft.quantum.glossary#superposition) $\ket ${0}nebo $\ket $ pokud je qubit zpočátku ve stavu $\ket $ . V Q# je tato operace použita [`H`](xref:microsoft.quantum.intrinsic.h) předdefinovanou operací.

## <a name="immutable"></a>Neměnná

Proměnná, jejíž hodnotu nelze změnit. Neměnná proměnná v Q# `let` je vytvořena pomocí klíčového slova. Chcete-li deklarovat proměnné, které *lze* změnit, `set` použijte [proměnlivé](xref:microsoft.quantum.glossary#immutable) klíčové slovo deklarovat a klíčové slovo upravit hodnotu. 

## <a name="measurement"></a>Měření

Manipulace s [qubitem](xref:microsoft.quantum.glossary#qubit) (nebo sadou qubitů), která dává výsledek pozorování, ve skutečnosti získává klasický bit. Další informace naleznete [v tématu Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Měnitelné

Proměnná, jejíž hodnota může být po vytvoření změněna. Proměnlivá proměnná v Q# `mutable` je deklarována pomocí klíčového slova a upravena pomocí klíčového `set` slova. Proměnné vytvořené pomocí `let` klíčového slova jsou [neměnné](xref:microsoft.quantum.glossary#immutable) a jejich hodnotu nelze změnit.

## <a name="namespace"></a>Obor názvů

Popisek pro kolekci souvisejících názvů (tj. [operace](xref:microsoft.quantum.glossary#operation), [funkce](xref:microsoft.quantum.glossary#function)a [uživatelem definované typy).](xref:microsoft.quantum.glossary#user-defined-type) Například obor názvů [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) označuje všechny symboly definované ve standardní knihovně, které pomáhají při přípravě počátečních stavů.

## <a name="operation"></a>Operace

Základní jednotka kvantové realizace v Q#. Je zhruba ekvivalentní funkci v Jazyce C, C++ nebo Pythonu nebo statické metodě v jazyce C# nebo v jazyce Java. Další informace naleznete v [tématu Operation and function types](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="operator-application"></a>Aplikace operátora

Provádím kvantovou operaci. To obvykle platí unitární matice na aktuální kvantový stav vektoru.

## <a name="oracle"></a>Oracle

Podprogram, který poskytuje informace závislé na datech kvantový algoritmus za běhu. Cílem je obvykle poskytnout [superpozici](xref:microsoft.quantum.glossary#superposition) výstupů odpovídajících vstupům, které jsou v superpozici. Další informace naleznete v [tématu Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Částečná aplikace

Volání [funkce](xref:microsoft.quantum.glossary#function) nebo [operace](xref:microsoft.quantum.glossary#operation) bez všech požadovaných vstupů. To vrátí nový [volatelný,](xref:microsoft.quantum.glossary#callable) který potřebuje pouze chybějící parametry (označené podtržítkem), které mají být dodány během budoucí aplikace. Například vzhledem `MyFunc(x : int, y : int) : int {return x + y;}` k funkci ji můžete částečně `let NewFunc = MyFunc(_, 3)`použít na novou funkci . Novou funkci pak můžete později volat s `NewFunc(2)` chybějícím parametrem, který vrací hodnotu *5*.  Další informace naleznete v tématu [Částečná aplikace](xref:microsoft.quantum.language.expressions#partial-application).

## <a name="pauli-operators"></a>Pauli operátoři

Sada tří 2 x 2 unitárních matic `X`známých jako , `Y` a `Z` kvantové operace. Matice identity, $I$, je často součástí sady také.  $I = \begin{bmatrix} \\ \\ 1 & 0 0 & 1 \end{bmatrix}$, $X \\ \\ = \begin{bmatrix} 0 & 1 1 & 0 \end{bmatrix}$, $Y = \begin{bmatrix} 0 & -i \\ \\ i & 0 \end{bmatrix}$, $Z = \begin{bmatrix} 1 & 0 \\ \\ 0 & -1 \bmatrix}$.   Další informace naleznete [v tématu Single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Kvantový schéma obvodu

Metoda graficky reprezentovat sekvenci [operací](xref:microsoft.quantum.glossary#operation) (nebo [brány)](xref:microsoft.quantum.glossary#gate)pro ![jednoduché](~/media/qpe.png)kvantové programy, například Ukázkový obvodový diagram . Další informace naleznete v tématu [Quantum circuits](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Kvantové knihovny

Kolekce [operací](xref:microsoft.quantum.glossary#operation), [funkce](xref:microsoft.quantum.glossary#function) a [uživatelem definované typy](xref:microsoft.quantum.glossary#user-defined-type) pro vytváření programů Q#. Standardní [knihovna](xref:microsoft.quantum.libraries.standard.intro) je nainstalována ve výchozím nastavení. Další knihovny jsou k dispozici [chemie knihovna](xref:microsoft.quantum.chemistry.concepts.intro), [numerická knihovna](xref:microsoft.quantum.numerics.intro) a [knihovna strojového učení](xref:microsoft.quantum.machine-learning.concepts.intro).

## <a name="quantum-state"></a>Kvantový stav

Přesný stav izolovaného kvantového systému, ze kterého lze extrahovat pravděpodobnosti [měření.](xref:microsoft.quantum.glossary#measurement) V kvantové výpočetní technice kvantový simulátor používá tyto informace k simulaci toho, jak qubity reagují na operace. Další informace naleznete [v tématu Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit

Základní jednotka kvantových informací, analogický k *trochu* v klasické výpočetní techniky. Další informace naleznete [v tématu Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Opakovat až do úspěchu

Kvantový algoritmus, který probabilisticky uspěje. Po selhání se rutina bude opakovat, dokud nebude úspěšná (nebo bylo dosaženo limitu). Další informace naleznete [v tématu Repeat Until Success (RUS)](xref:microsoft.quantum.techniques.qubits#measurements)

## <a name="standard-libraries"></a>Standardní knihovny

[Operace](xref:microsoft.quantum.glossary#operation), [funkce](xref:microsoft.quantum.glossary#function) a [uživatelem definované typy,](xref:microsoft.quantum.glossary#user-defined-type) které jsou nainstalovány spolu s kompilátorem Q# během instalace. Standardní implementace knihovny je agnostik s ohledem na cílové počítače. Další informace naleznete v [tématu Standardní knihovny](xref:microsoft.quantum.libraries.standard.intro).

## <a name="superposition"></a>Superpozice

Koncept kvantové výpočetní techniky, že [qubit](xref:microsoft.quantum.glossary#qubit) je lineární kombinace dvou stavů, $\ket{\\} a $\ket{\1}$, dokud není [měřen](xref:microsoft.quantum.glossary#measurement).  Další informace naleznete v tématu [Co je kvantová výpočetní technika](xref:microsoft.quantum.overview.what).

## <a name="target-machine"></a>Cílový stroj

Cíl kompilace, který snižuje abstraktní kvantový program směrem k hardwaru nebo simulaci. To obvykle zahrnuje přepisování pro mnoho účelů, včetně nahrazení brány, kódování pro opravu chyb, geometrické rozložení a další. Další informace naleznete v [tématu Quantum simulátory a hostitelské aplikace](xref:microsoft.quantum.machines).

## <a name="teleportation"></a>Teleportace

Metoda regenerace dat nebo [kvantového stavu](xref:microsoft.quantum.glossary#quantum-state)jednoho [qubitu](xref:microsoft.quantum.glossary#qubit) z jednoho místa na druhé bez fyzického pohybu qubitu pomocí [zapletení](xref:microsoft.quantum.glossary#entanglement) a [měření](xref:microsoft.quantum.glossary#measurement).  Další informace naleznete v [tématech Kvantové obvody](xref:microsoft.quantum.concepts.circuits) a [Uvedení to všechno dohromady](xref:microsoft.quantum.techniques.puttingittogether).

## <a name="tuple"></a>Tuple

Kolekce hodnot oddělených čárkami, která funguje jako jedna hodnota. *Typ* řazené kolekce členů je definován typy hodnot, které obsahuje. V Q#jsou řazené kolekce členů [neměnné](xref:microsoft.quantum.glossary#immutable) a mohou být vnořeny, obsahovat pole nebo použity v poli. Další informace naleznete v tématu [Typy tuple](xref:microsoft.quantum.language.type-model#tuple-types).

## <a name="unitary-operator"></a>Unitární operátor

Operátor $UU, jehož inverzní je rovna jeho [adjoint](xref:microsoft.quantum.glossary#adjoint), tj.

## <a name="user-defined-type"></a>Uživatelem definovaný typ

Kolekce předdefinované nebo dříve definované typy, které mohou být označovány jako jedna jednotka. Další informace naleznete v [tématu User-defined types](xref:microsoft.quantum.language.type-model#user-defined-types).