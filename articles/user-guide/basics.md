---
title: Q# Práce
description: Základní koncepty Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: b3bc0841eabeac5d3968776f9dab3a02b1a1eef9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691632"
---
# <a name="no-locq-basics"></a>Q# Práce

Tento článek představuje stručný úvod do základních stavebních bloků Q# .

Přehled toho, co je to Q# a kde se zahodí jako základní součást sady pro vývoj pro všechna množství, najdete v tématu [co je Q# ?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Co je program pro vydaných hodnot?

Z technického hlediska je program pro práci s více operačními systémy konkrétní sadou klasických podprocesů, které při volání provádějí určité operace s operačním systémem.
Důležitým rozdílem v tomto zobrazení je, že Q# program přímo nemodeluje qubits sám sebe, ale místo toho popisuje, jak klasický kontrolovaný počítač komunikuje s těmito qubits.
Podle návrhu Q# nedefinuje stavy plnění nebo jiné vlastnosti přístavení přímo.
Zvažte například stav $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ popsané v tématu Průvodce přístupnými [výpočetními pojmy](xref:microsoft.quantum.concepts.intro) .
Chcete-li tento stav připravit v Q# , začněte s fakty, že qubits jsou inicializovány ve {0} stavu $ \ket $ a že $ \ket{+} = H\ket {0} $, kde $H $ je [Převod Hadamard](xref:microsoft.quantum.glossary#hadamard), implementovaný [ `H` operací](xref:Microsoft.Quantum.Intrinsic.H). Základní Q# kód pro inicializaci a transformaci qubit a pak vypadá takto:

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
Další informace o inicializaci nebo *přidělování* qubits naleznete v tématu [Working with qubits](xref:microsoft.quantum.guide.qubits).

## <a name="quantum-states-in-no-locq"></a>Stavy v Q#

Důležité: předchozí program výslovně neodkazuje na stav v rámci, Q# ale popisuje, jak náš program *transformoval* stav.
Díky tomuto přístupu můžete být zcela nezávislá o tom, co *je* stav bez limitu, i na každém cílovém počítači, což může mít různé interpretace v závislosti na počítači. 

Q#Program se nemůže introspect do stavu qubit.
Místo toho může program volat operace, jako je například, [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) k získání informací z qubit a volání operací, jako je [`X`](xref:Microsoft.Quantum.Intrinsic.X) a [`H`](xref:Microsoft.Quantum.Intrinsic.H) k jednání ve stavu qubit.
K *tomu* , aby tyto operace skutečně fungovaly, se dá použít jenom konkrétní cílový počítač, který se používá ke spuštění konkrétního Q# programu.
Pokud například spustíte program na našem simulátoru, simulátor provede odpovídající matematické operace do simulovaného systému pro [nastavování](xref:microsoft.quantum.machines.full-state-simulator).
Ale prohlížíte se do budoucna, když je cílový počítač skutečným počítačem s více operačními systémy, volání těchto operací v Q# systému směruje počítač s operačním systémem do provozu, aby provedl odpovídající *reálné* operace v *reálném čase* , například přesné časované laserové impulsy.

Q#Program znovu sloučí tyto operace, jak jsou definovány cílovým počítačem, a vytvoří tak nové operace vyšší úrovně pro expresní výpočty.
Tímto způsobem Q# usnadňuje vyjádření logiky podkladových a hybridních neřízených – klasických a běžných algoritmů, a to i v souvislosti s strukturou cílového počítače nebo simulátoru.

## <a name="no-locq-operations-and-functions"></a>Q# operace a funkce

Konkrétní Q# program zahrnuje *operace* , *funkce* a libovolné uživatelsky definované typy. 

Operace slouží k popisu transformací systémů pro plnění a jsou nejdůležitějším stavebním blokem Q# programů. Každá operace definovaná v nástroji Q# může zavolat libovolný počet dalších operací.

Na rozdíl od operací se funkce používají k popisu čistě *deterministického* klasického chování a neexistují žádné vlivy na výpočetní funkce Classic. Předpokládejme například, že chcete změřit qubits na konci programu a přidat výsledky měření do pole.
V tomto případě `Measure` je to *operace* , která instruuje cílový počítač, aby provedl měření na (reálné nebo simulované) qubits. Ve stejnou dobu *funkce* zpracovávají klasický proces přidávání vrácených výsledků do pole.

Operace a funkce se společně označují jako *volatelné* . Jejich podkladová struktura a chování jsou zavedeny a podrobně popsány v [operacích a funkcích v Q# ](xref:microsoft.quantum.guide.operationsfunctions).


## <a name="no-locq-syntax-overview"></a>Q# Přehled syntaxe

Syntaxe jazyka popisuje různé kombinace symbolů, které tvoří syntakticky správný program.
V nástroji Q# prvky syntaxe jsou klasifikovány do tří různých skupin: typy, výrazy a příkazy.

### <a name="types"></a>Typy
Q# je jazyk silného typu, aby mohl kompilátor poskytovat silné záruky týkající se Q# programů v době kompilace, může to přispět k pečlivému použití typů.
Kromě standardních a vestavěných primitivních typů, například,, a `Int` `Bool` `Qubit` `Result` , Q# poskytuje podporu pro uživatelsky definované typy.

Popisy všech primitivních typů, podrobnosti o typech pole a řazené kolekce členů a kroky pro definování nových typů v rámci Q# souboru naleznete [v tématu typy Q# v ](xref:microsoft.quantum.guide.types).

### <a name="expressions"></a>Výrazy
Výraz v programovacím jazyce je kombinací jedné nebo více konstant, proměnných, operátorů a funkcí, které programovací jazyk interpretuje a vyhodnocuje na konkrétní hodnotu.
Nejvíce jednoduché pro každý typ v jazyce, výrazy tohoto typu mohou být buď *literály* , nebo symboly vázané na hodnotu daného typu.
Například `5` je `Int` literál (tedy také výraz typu `Int` ), a pokud `count` je symbol svázán s celočíselnou hodnotou `5` , `count` je také výraz celého čísla.

Kromě toho výraz může obsahovat jiné výrazy kombinované konkrétními operátory.
Například jiný `Int` výraz, který je vyhodnocen jako `5` `2+3` .

Další informace o výrazech a kompatibilních operátorech v naleznete v Q# tématu [výrazy typu Q# v ](xref:microsoft.quantum.guide.expressions). 

### <a name="statements"></a>Příkazy 
Příkaz je syntaktickou jednotkou imperativního programovacího jazyka, která vyjadřuje určitou akci pro provedení. Příkazy na rozdíl od výrazů v těchto příkazech nevracejí výsledky a jsou spouštěny výhradně pro své vedlejší účinky. Výrazy ale vždycky vracejí výsledek a často nemají žádné vedlejší účinky. V krátké Q# době jsou příkazy spouštěny, zatímco jsou výrazy vyhodnocovány.

Jednoduchý příklad příkazu v nástroji Q# přiřazuje symbol ke výrazu:
```qsharp
let count = 5;
```

Zajímavějším příkladem je `for` příkaz, který podporuje iteraci a obsahuje *blok příkazu* .
Předpokládejme `qubits` je symbol vázaný k registru qubits (technicky typu `Qubit[]` nebo pole `Qubit` typů). Pak...
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
je příkaz, který prochází každou qubit v registru a provádí `H` operaci na každém z nich. Všimněte si, že `H(qubit);` je také samotný příkaz.

Můžete použít libovolný výraz volání typu `Unit` ( `Unit` typ nevrací žádné informace) jako příkaz.
Tento typ výrazu je užitečný při volání operací na qubits, která se vrátí, `Unit` protože účelem příkazu je upravit implicitní stav.
Příkazy vyhodnocení výrazu vyžadují ukončující středník.

Příkazy můžete použít k sestavení téměř všech aspektů Q# programu a žádná jediná stránka by nemohla zahrnovat všechny informace, které se na ně vztahují.
Další informace o jejich lexikální struktuře a formátování naleznete v tématu [ Q# struktura souborů](xref:microsoft.quantum.guide.filestructure); informace o přiřazení a rozsahu vazby symbolů naleznete [v tématu Q# Variables in ](xref:microsoft.quantum.guide.variables)a pro smyčky toku řízení, například `for` , [v tématu řízení toku Q# v ](xref:microsoft.quantum.guide.controlflow).

## <a name="next-steps"></a>Další kroky

Začněte se učit o [typech Q# v ](xref:microsoft.quantum.guide.types).

Další informace o základech a motivaci na pozadí Q# najdete v tématu [Proč to Q# ](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)potřebujeme.
