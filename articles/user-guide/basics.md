---
title: 'Základy Q #'
description: 'Základní koncepty Q #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: 45e6f2f33dafc2aec177091d3cfa94aca14fbf0a
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415352"
---
# <a name="q-basics"></a>Základy Q #

Tento článek představuje stručný úvod do základních stavebních bloků Q #.

Základní informace o tom, co je otázka č. Q a kde se zahodí jako základní komponenta vývojové sady pro plnění, najdete v tématu [co je q #?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Co je program pro vydaných hodnot?

Z technického hlediska je program pro práci s více operačními systémy konkrétní sadou klasických podprocesů, které při volání provádějí určité operace s operačním systémem.
Důležitým rozdílem v tomto zobrazení je, že program Q # přímo nemodeluje qubits sám sebe, ale místo toho popisuje, jak počítač s klasickým kontrolovaným počítačem komunikuje s těmito qubits.
V důsledku návrhu Q # nedefinuje stavy, které jsou ve stavu plnění, ani jiné vlastnosti nevýrobního mechanismu.
Zvažte například stav $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ popsané v tématu Průvodce přístupnými [výpočetními pojmy](xref:microsoft.quantum.concepts.intro) .
Chcete-li tento stav připravit v Q #, začněte s fakty, že qubits jsou inicializovány ve {0} stavu $ \ket $ a že $ \ket{+} = H\ket {0} $, kde $H $ je [Převod Hadamard](xref:microsoft.quantum.glossary#hadamard), implementovaný [ `H` operací](xref:microsoft.quantum.intrinsic.h). Kód Basic Q # pro inicializaci a transformaci qubit a pak vypadá takto:

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
Další informace o inicializaci nebo *přidělování*qubits naleznete v tématu [Working with qubits](xref:microsoft.quantum.guide.qubits).

## <a name="quantum-states-in-q"></a>Stavy v Q #

Důležité je, že předchozí program výslovně neodkazuje na stav ve Q #, ale popisuje, jak náš program *transformoval* stav.
Díky tomuto přístupu můžete být zcela nezávislá o tom, co *je* stav bez limitu, i na každém cílovém počítači, což může mít různé interpretace v závislosti na počítači. 

Program Q # se nemůže introspect do stavu qubit.
Místo toho může program volat operace, jako je například, [`Measure`](xref:microsoft.quantum.intrinsic.measure) k získání informací z qubit a volání operací, jako je [`X`](xref:microsoft.quantum.intrinsic.x) a [`H`](xref:microsoft.quantum.intrinsic.h) k jednání ve stavu qubit.
K *tomu* , aby tyto operace skutečně fungovaly, se dá použít jenom konkrétní cílový počítač, který se používá ke spuštění konkrétního programu Q #.
Pokud například spustíte program na našem simulátoru, simulátor provede odpovídající matematické operace do simulovaného systému pro [nastavování](xref:microsoft.quantum.machines.full-state-simulator).
Ale když je cílový počítač skutečným počítačem, který se blíží k budoucnosti, volání těchto operací v Q # směruje počítač s příznakem do provozu, aby prováděl odpovídající *reálné* operace v *reálném čase* , například přesné časované laserové impulsy.

Program Q # znovu sloučí tyto operace, jak jsou definovány cílovým počítačem, a vytvoří tak nové operace vyšší úrovně, které budou vyjadřovat výpočetní procesory.
V tomto případě Q # usnadňuje vyjádření logiky podkladových a hybridních životních stojí – klasických algoritmů, a to i v souvislosti se strukturou cílového počítače nebo simulátoru.

## <a name="q-operations-and-functions"></a>Operace a funkce Q #

Program Q # sestává z konkrétního typu *operací*, *funkcí*a všech uživatelem definovaných typů. 

Operace slouží k popisu transformací systémů pro plnění a jsou nejdůležitějším stavebním blokem programů Q #. Každá operace definovaná v Q # může potom zavolat libovolný počet dalších operací.

Na rozdíl od operací se funkce používají k popisu čistě *deterministického* klasického chování a neexistují žádné vlivy na výpočetní funkce Classic. Předpokládejme například, že chcete změřit qubits na konci programu a přidat výsledky měření do pole.
V tomto případě `Measure` je to *operace* , která instruuje cílový počítač, aby provedl měření na (reálné nebo simulované) qubits. Ve stejnou dobu *funkce* zpracovávají klasický proces přidávání vrácených výsledků do pole.

Operace a funkce se společně označují jako *volatelné*. Jejich podkladová struktura a chování jsou zavedeny a podrobně popsány v [operacích a funkcích v Q #](xref:microsoft.quantum.guide.operationsfunctions).


## <a name="q-syntax-overview"></a>Přehled syntaxe Q #

Syntaxe jazyka popisuje různé kombinace symbolů, které tvoří syntakticky správný program.
V Q # prvky syntaxe jsou klasifikovány do tří různých skupin: typy, výrazy a příkazy.

### <a name="types"></a>Typy
Q # je jazyk silného typu, který může při kompilaci poskytnout pečlivou možnost použití typů za účelem poskytnutí silné záruky na programy Q #.
Kromě standardních a vestavěných primitivních typů, například,, a `Int` `Bool` `Qubit` `Result` , Q #, poskytuje podporu pro uživatelsky definované typy.

Popisy všech primitivních typů, podrobností pro typy polí a řazené kolekce členů a kroky pro definování nových typů v souboru Q # naleznete v tématu [typy v Q #](xref:microsoft.quantum.guide.types).

### <a name="expressions"></a>Výrazy
Výraz v programovacím jazyce je kombinací jedné nebo více konstant, proměnných, operátorů a funkcí, které programovací jazyk interpretuje a vyhodnocuje na konkrétní hodnotu.
Nejvíce jednoduché pro každý typ v jazyce, výrazy tohoto typu mohou být buď *literály* , nebo symboly vázané na hodnotu daného typu.
Například `5` je `Int` literál (tedy také výraz typu `Int` ), a pokud `count` je symbol svázán s celočíselnou hodnotou `5` , `count` je také výraz celého čísla.

Kromě toho výraz může obsahovat jiné výrazy kombinované konkrétními operátory.
Například jiný `Int` výraz, který je vyhodnocen jako `5` `2+3` .

Další informace o výrazech a kompatibilních operátorech v Q # naleznete v tématu [Expression Types in q #](xref:microsoft.quantum.guide.expressions). 

### <a name="statements"></a>Příkazy 
Příkaz je syntaktickou jednotkou imperativního programovacího jazyka, která vyjadřuje určitou akci pro provedení. Příkazy na rozdíl od výrazů v těchto příkazech nevracejí výsledky a jsou spouštěny výhradně pro své vedlejší účinky. Výrazy ale vždycky vracejí výsledek a často nemají vedlejší účinky. V krátkých příkazech Q # se spustí, zatímco se vyhodnotí výrazy.

Jednoduchým příkladem příkazu v Q # je přiřazení symbolu k výrazu:
```qsharp
let count = 5;
```

Zajímavějším příkladem je `for` příkaz, který podporuje iteraci a obsahuje *blok příkazu*.
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

Příkazy můžete použít k sestavení téměř všech aspektů programu Q # a žádná jediná stránka by nemohla zahrnovat všechny informace, které se na ně vztahují.
Další informace o jejich lexikální struktuře a formátování najdete v tématu [struktura souborů Q #](xref:microsoft.quantum.guide.filestructure); informace o přiřazení a rozsahu vazby symbolů naleznete [v tématu proměnné v Q #](xref:microsoft.quantum.guide.variables);. a pro smyčky toku řízení `for` , například, viz [tok řízení v Q #](xref:microsoft.quantum.guide.controlflow).

## <a name="next-steps"></a>Další kroky

Začněte se učit o [typech v Q #](xref:microsoft.quantum.guide.types).

Další informace o základech a motivaci za Q # najdete v tématu [Proč musíme q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
