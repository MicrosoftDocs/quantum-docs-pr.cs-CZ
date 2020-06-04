---
title: 'Základy Q #'
description: 'Základní koncepty Q #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: e77b52d1a6eb7e2f62ab12dedd75d00ac8fec4be
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327318"
---
# <a name="q-basics"></a>Základy Q #

V této části uvádíme stručný úvod do základních stavebních bloků Q #.

Pokud potřebujete rychlý přehled toho, co je Q # a kde se zahodí jako základní součást sady pro vývoj pro všechna množství, můžete zjistit, [co je q #?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Co je program pro vydaných hodnot?

Z technického hlediska je program pro práci s více operačními systémy zobrazený jako konkrétní sada klasických podprocesů, které při volání provádějí určité operace s operačním systémem.
Důležitým vlivem tohoto zobrazení je to, že program napsaný v Q # přímo nemodeluje qubits sám sebe, ale místo toho popisuje, jak počítač s klasickým ovládacím prvkem komunikuje s těmito qubits.
Podle návrhu, Q # proto nedefinuje stavy, které jsou ve stavu plnění, ani jiné vlastnosti nestavového mechanismu.
Zvažte například stav $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ popsané v tématu Průvodce přístupnými [výpočetními pojmy](xref:microsoft.quantum.concepts.intro) .
Chcete-li tento stav připravit v Q #, používáme fakty, že qubits jsou inicializovány ve {0} stavu $ \ket $ a že $ \ket{+} = H\ket {0} $, kde $H $ je převod Hadamard, implementovaný pomocí [ `H` operace] (] (odkazy XREF: Microsoft. NázevOperace. vnitřní. H):

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a>Stavy v Q #

Při psaní výše uvedeného programu jsme v rámci tohoto programu explicitně neodkazovali na stav ve Q #, ale místo toho jsme popsali, jak byl stav *transformován* náš program.
To nám umožní zcela nezávislá informace o tom, co *je* stav bez nároku na každém cílovém počítači, což může mít různé interpretace v závislosti na počítači. 

Program Q # nemá žádnou schopnost introspect do stavu qubit.
Program může spíše volat operace, jako je například, [`Measure`](xref:microsoft.quantum.intrinsic.measure) k získání informací z qubit a volání operací, jako je [`X`](xref:microsoft.quantum.intrinsic.x) a [`H`](xref:microsoft.quantum.intrinsic.h) k jednání ve stavu qubit.
Díky *tomu* se tyto operace skutečně provádějí jenom v cílovém počítači, který používáme ke spuštění konkrétního programu Q #.
Například pokud je program spuštěný v [celém kompletním simulátoru](xref:microsoft.quantum.machines.full-state-simulator), simulátor provede odpovídající matematické operace do simulovaného systému.
Ale pokud je cílový počítač skutečným počítačem, který se blíží k budoucnosti, volání takových operací v Q # nasměruje počítač s příznakem do provozu, aby provedl odpovídající *reálné* operace v *reálném* systému doby provozu (například přesně časované laserové Pulse).

Program Q # znovu sloučí tyto operace, jak jsou definovány cílovým počítačem, a vytvoří tak nové operace vyšší úrovně, které budou vyjadřovat výpočetní procesory.
V tomto případě Q # usnadňuje vyjádření logiky podkladových a hybridních životních stojí – klasických algoritmů, a to i v souvislosti se strukturou cílového počítače nebo simulátoru.

## <a name="q-operations-and-functions"></a>Operace a funkce Q #

V betonu se program Q # skládá z *operací*, *funkcí*a libovolných uživatelsky definovaných typů. 

Operace se používají k popisu transformací systémů a jsou to nejzákladnější stavební bloky programů Q #. Každá operace definovaná v Q # může potom zavolat libovolný počet dalších operací.

Na rozdíl od operací se funkce používají k popisu čistě *deterministického* klasického chování a neexistují žádné vlivy na výpočetní funkce Classic. Předpokládejme například, že byste chtěli změřit naše qubits na konci programu a přidat výsledky měření do pole.
V tomto případě `Measure` je to *operace* , která instruuje cílový počítač, aby provedl měření na (reálné nebo simulované) qubits a klasický proces přidávání vrácených výsledků do pole bude zpracován *funkcí Functions*.

Operace a funkce jsou společně označovány jako *volatelné*a jejich podkladová struktura a chování se zavádějí na [operace a funkce na stránce Q #](xref:microsoft.quantum.guide.operationsfunctions) .


## <a name="q-syntax-overview"></a>Přehled syntaxe Q #

Syntaxe jazyka popisuje různé kombinace symbolů, které tvoří syntakticky správný program.
V Q # můžeme klasifikovat prvky své syntaxe ve třech různých skupinách: typy, výrazy a příkazy.

### <a name="types"></a>Typy
Q # je jazyk silného typu, který může při kompilaci poskytnout pečlivou možnost použití typů za účelem poskytnutí silné záruky na programy Q #.
Kromě standardních a vestavěných primitivních typů (např.,, `Int` `Bool` `Qubit` a `Result` ) v případě, že Q # poskytuje podporu pro uživatelsky definované typy.
Všechny primitivní typy "Q #" jsou popsány na stránce [typy v souboru q #](xref:microsoft.quantum.guide.types) spolu s podrobnostmi o typech polí a řazené kolekce členů a také o tom, jak definovat nové typy v souboru Q #.

### <a name="expressions"></a>Výrazy
Výraz v programovacím jazyce je kombinací jedné nebo více konstant, proměnných, operátorů a funkcí, které programovací jazyk interpretuje a vyhodnocuje na konkrétní hodnotu.
Nejvíce jednoduché pro každý typ v jazyce, výrazy tohoto typu mohou být buď *literály* , nebo symboly vázané na hodnotu daného typu.
Například `5` je `Int` literál (tedy také výraz typu `Int` ), a pokud `count` je symbol svázán s celočíselnou hodnotou `5` , `count` je také výraz celého čísla.

Kromě toho se výraz může skládat z dalších výrazů v kombinaci s určitými operátory.
Proto další příklad `Int` výrazu, který je vyhodnocen jako `5` `2+3` .

Možné výrazy typů v Q # a také kompatibilní operátory, které lze použít pro jejich vytvoření, jsou popsány na [výrazech typu na stránce Q #](xref:microsoft.quantum.guide.expressions) . 

### <a name="statements"></a>Příkazy 
Příkaz je syntaktickou jednotkou imperativního programovacího jazyka, která vyjadřuje určitou akci, která má být provedena. Příkazy kontrastující s výrazy v těchto příkazech nevrací výsledky a jsou spouštěny výhradně pro své vedlejší účinky, zatímco výrazy vždy vracejí výsledek a často nemají vedlejší účinky.
Tento rozdíl je často pozorován ve slovech: je vyhodnocen výraz, zatímco je proveden příkaz.

Velmi základní příklad příkazu v Q # přiřazuje k výrazu symbol:
```qsharp
let count = 5;
```

Trochu zajímavější příklad je `for` příkaz, který podporuje iteraci a obsahuje *blok příkazu*.
Předpokládejme `qubits` je symbol vázaný k registru qubits (technicky typu `Qubit[]` , tj. pole `Qubit` typů). Pak...
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
je příkaz, který projde každou qubit v registru a provede `H` operaci na každém z nich. Všimněte si, že `H(qubit);` je také samotný příkaz.

Ve skutečnosti `Unit` může být jako příkaz použit libovolný výraz volání typu (ty, které se dají volat, které nevracejí žádné informace).
To je primárně použito při volání operací na qubits, které vracejí, `Unit` protože účel příkazu je upravit implicitní stav nečinnosti.
Příkazy vyhodnocení výrazu vyžadují ukončující středník.

Skoro každý aspekt programu Q # je sestaven pomocí příkazů, takže žádná z nich nemůže zahrnovat všechny informace, které se na ně vztahují.
Jejich lexikální struktura a formátování jsou však popsány na stránce [struktury souborů q #](xref:microsoft.quantum.guide.filestructure) , přiřazení symbolů a rozsahu u [proměnných v q #](xref:microsoft.quantum.guide.variables)a v cyklech toku řízení, jako je `for` například [tok řízení v q #](xref:microsoft.quantum.guide.controlflow).

## <a name="next-steps"></a>Další kroky
V celé zbývající části tohoto průvodce vám ukážeme, jak pomocí Q # vytvářet komplexní programy pro vystavování prostřednictvím základních stavebních bloků operací, funkcí a typů.

Pokud chcete začít, můžete začít učit se o [typech v Q #](xref:microsoft.quantum.guide.types).

Pokud vás zajímá více o základech a motivaci za Q #, podívejte se, [Proč musíme q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
