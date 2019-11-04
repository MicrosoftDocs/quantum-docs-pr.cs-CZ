---
title: 'Průvodce stylem Q # | Microsoft Docs'
description: 'Průvodce stylem Q #'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 56455e9d5cd452b8620ee794f40563d1d3040193
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183841"
---
# <a name="q-style-guide"></a>Průvodce stylem Q # #
## <a name="general-conventions"></a>Obecné konvence ##

Konvence navržené v této příručce jsou určené k tomu, aby usnadnily čtení a pochopení programů a knihoven ve službě Q #.

# <a name="guidancetabguidance"></a>[Doprovodné materiály](#tab/guidance)

Navrhujeme:

- Nikdy nepoužívejte konvenci, pokud to neprovedete záměrně za účelem poskytnutí čitelnějšího a srozumitelného kódu pro uživatele.

# <a name="examplestabexamples"></a>[Příklady](#tab/examples)

***

## <a name="naming-conventions"></a>Zásady vytváření názvů ##

V rámci nabídky vývojové sady pro práci s více operačními společnostmi usilujeme o názvy funkcí a operací, které vývojářům usnadňují psaní programů, které se snadno čtou a které minimalizují neočekávaně.
Důležitou součástí toho je, že když vybíráme názvy pro funkce, operace a typy, vytvoříme *slovník* , který programátoři používají pro vyjádření základních konceptů. Díky našim možnostem vám pomůžeme nebo je bráníme v jejich úsilí, aby mohli jasně komunikovat.
Tím se na nás zaručí zodpovědnost, aby se zajistilo, že názvy, které zavádíme, představují srozumitelnější místo neprůhlednosti.
V této části podrobně uvádíme, jak splňujeme tuto povinnost z hlediska explicitních pokynů, abychom nám mohli co nejlépe udělat komunitou pro vývoj Q.

### <a name="operations-and-functions"></a>Operace a funkce ###

Jedna z prvních věcí, které by měl název vytvořit, je, zda daný symbol představuje funkci nebo operaci.
Rozdíl mezi funkcemi a operacemi je zásadní pro porozumění způsobu, jakým se chová blok kódu.
Pro sdělování rozdílů mezi funkcemi a operacemi pro uživatele spoléháme na to, že modely Q # využívají vedlejší účinky na tyto operace.
To znamená, že operace *dělá* něco.

Naopak funkce popisují matematické vztahy mezi daty.
Výraz `Sin(PI() / 2.0)` *je* `1.0`a nevyjadřuje žádné informace o stavu programu nebo jeho qubits.

Sumarizace, operace se provádí v době, kdy jsou funkce věcí.
Tento rozdíl naznačuje, že pojmenování operací jako operací a funkcí jako podstatných jmen.

> [!NOTE]
> Když je deklarován uživatelsky definovaný typ, je nová funkce, která vytváří instance daného typu, implicitně definována současně.
> Z této perspektivy by měly být uživatelsky definované typy pojmenovány jako podstatná jména, aby samotný typ i funkce konstruktoru měly konzistentní názvy.

Tam, kde je to rozumné, zajistěte, aby názvy operací začaly slovesy, které jasně indikují účinek prováděný operací.
Například:

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

Jeden případ, který zachovává zvláštní zmínku, je v případě, že operace přebírá jinou operaci jako vstup a volá ji.
V takových případech není akce prováděná vstupní operací jasná, když je definovaná vnější operace, takže není správná operace okamžitě jasná.
Jako v `ApplyIf`, `ApplyToEach`a `ApplyToFirst`doporučujeme použít příkaz `Apply`.
V tomto případě mohou být užitečné i jiné akce, jako v `IterateThroughCartesianPower`.

| Operace | Očekávaný efekt |
| ---- | ------ |
| Použít | Nazývá se operace zadaná jako vstup. |
| Uplatňuje | Hypotéza o výsledku možného měření doby využívání se kontroluje simulátorem. |
| Ocenění | Vrátí se klasická hodnota, která představuje odhad vykreslený z jedné nebo více měření. |
| Měrné | Měří se měření po sobě a výsledek se vrátí uživateli. |
| Připravit | Daný registr qubits se inicializuje do určitého stavu. |
| Ukázka | Z nějaké distribuce se náhodně vrátí klasická hodnota. |

V případě funkcí doporučujeme vyhnout se použití sloves ve prospěch běžných podstatných jmen (viz doprovodné materiály o řádných podstatných jmenách níže) nebo adjektiva:

- `ConstantArray`
- `Head`
- `LookupFunction`

Konkrétně v téměř všech případech doporučujeme použít dřívější participles, kde je to vhodné k označení toho, že název funkce je důrazně připojen k akci nebo vedlejšímu účinku jinde v programu pro práci s více událostmi.
Například `ControlledOnInt` používá participle formuláře příkazu "Control" k označení toho, že funkce funguje jako adjektivum pro úpravu svého argumentu.
Tento název má další výhody, které odpovídají sémantikě předdefinovaných `Controlled` funktor, jak je popsáno dále níže.
Obdobně lze použít _substantivum agenta_ k vytvoření funkce a názvů UDT z názvů operací, jako v případě názvu `Encoder` pro UDT, který je silně spojen s `Encode`.

# <a name="guidancetabguidance"></a>[Doprovodné materiály](#tab/guidance)

Navrhujeme:

- Pro názvy operací použijte slovesa.
- Pro názvy funkcí použijte podstatná jména nebo jména.
- Používejte podstatná jména pro uživatelsky definované typy a atributy.
- Pro všechny názvy, které lze volat, použijte `CamelCase` ve silném předvolbách na `pascalCase`, `snake_case`nebo `ANGRY_CASE`. Konkrétně se ujistěte, že názvy, které se budou volat, začínají velkým písmenem.
- U všech místních proměnných použijte `pascalCase` v případě silné Předvolby na `CamelCase`, `snake_case`nebo `ANGRY_CASE`. Konkrétně zajistěte, aby místní proměnné byly začínat malými písmeny.
- Vyhněte se použití podtržítek `_` v názvech funkcí a operací; v případě potřeby dalších úrovní hierarchie použijte obory názvů a aliasy oboru názvů.

# <a name="examplestabexamples"></a>[Příklady](#tab/examples)

|   | Name (Název) | Popis |
|---|------|-------------|
| ☑ | `operation ReflectAboutStart` | Zrušením použití příkazu ("reflektování") označíte účinek operace. |
| ☒ | <s>`operation XRotation`</s> | Místo operace použijte funkci navrhuje fráze substantivum. |
| ☒ | <s>`operation search_oracle`</s> | Použití `snake_case` je v rozporu s zápisem Q #. |
| ☒ | <s>`operation Search_Oracle`</s> | Použití podtržítek s podtržítkem pro název operace je v rozporu s zápisem Q #. |
| ☑ | `function StatePreparationOracle` | Použití fráze substantivum naznačuje, že funkce vrátí operaci. |
| ☑ | `function EqualityFact` | Zrušte použití podstatného jména ("fakt"), abyste označili, že se jedná o funkci, ale jeho jméno. |
| ☒ | <s>`function GetRotationAngles`</s> | Použití příkazu ("Get") naznačuje, že se jedná o operaci. |
| ☑ | `newtype GeneratorTerm` | Použití fráze substantivum jasně odkazuje na výsledek volání konstruktoru UDT. |
| ☒ | <s>`@Attribute() newtype RunOnce()`</s> | Použití příkazového fráze navrhuje, že konstruktor UDT je operace. |
| ☑ | `@Attribute() newtype Deprecated(Reason : String)` | Použití fráze substantivum komunikuje s použitím atributu. |

***

### <a name="shorthand-and-abbreviations"></a>Zkratky a zkratky ###

Výše uvedená doporučení se neshoduje, existuje mnoho forem zkrácených ve formě běžných a pervasivech použití ve výpočetním prostředí.
Doporučujeme používat existující a běžnou zkrácený popis, kde existuje, zejména pro operace, které jsou vnitřní pro provoz cílového počítače.
Například zvolíme název `X` místo `ApplyX`a `Rz` místo `RotateAboutZ`.
Při použití takových zkratek by názvy operací měly být všechna velká (např.: `MAJ`).

Při použití této konvence v případě běžně používaných akronymů a initialisms, jako je například "QFT", se vyžaduje určitá péče.
Pro použití akronymů a initialisms v úplných názvech doporučujeme následující obecné konvence rozhraní .NET, které předepisuje, že:

- zkratky se dvěma písmeny a initialisms se nazývají v horním případě (např.: `BE` pro "big-endian").
- všechny delší akronymy a initialisms se pojmenují v `CamelCase` (např.: `Qft` pro "dobu" s "Fourierova transformace").

Proto operace implementující QFT může být buď volána `QFT` jako zkrácený, nebo jako `ApplyQft`zapsána jako.

Pro obzvlášť používané operace a funkce může být vhodné zadat zkrácený název jako _alias_ pro delší tvar:

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidancetabguidance"></a>[Doprovodné materiály](#tab/guidance)

Navrhujeme:

- V případě potřeby zvažte běžně přijatelné a často používané zkrácený název.
- Pro zkrácený tvar použijte velká písmena.
- Používejte velká písmena pro krátká (dvě písmena) zkratky a initialisms.
- Použijte `CamelCase` pro delší (tři nebo více písmen) a initialisms.

# <a name="examplestabexamples"></a>[Příklady](#tab/examples)

|   | Name (Název) | Popis |
|---|------|-------------|
| ☑ | `X` | Dobře srozumitelná zkrácený příkaz pro použití transformace $X $ |
| ☑ | `CNOT` | Dobře srozumitelná zkrácená zkratka pro "řízená – ne" |
| ☒ | <s>`Cnot`</s> | Zkrácený odkaz by neměl být v `CamelCase`. |
| ☑ | `ApplyQft` | Běžným počátečním názvem "QFT" se jeví jako součást formátu dlouhého formátu. |
| ☑ | `QFT` | Common initialer "QFT" se zobrazuje jako součást zkrácený název. |



***


### <a name="proper-nouns-in-names"></a>Správná jména v názvech ###

V rámci fyziky je běžné pojmenování po první osobě, která o nich je publikovaná, většina nephysicistsch není obeznámená s názvy všech a všech historií.
Velmi silně spoléhá na konvence pojmenování z fyziky, takže by se měla zabývat značnou překážkou vstupu, protože uživatelé z jiných pozadí se musí seznámit s velkým počtem zdánlivě neprůhledných názvů, aby mohli používat běžné operace a koncepty.
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
Proto doporučujeme, abyste při každém rozumném a běžném výskytu, který popisuje pojem koncept, přijali v rámci silné Předvolby na řádné podstatné jméno, které popisují historii publikace konceptu.
Jako konkrétní příklad se v rámci akademické literatury často označují samostatně kontrolované SWAPy a dvakrát kontrolované operace, ale v rámci Fredkin se identifikují hlavně jako `CSWAP` a `CCNOT`.
V obou případech komentáře k rozhraní API poskytují synonymum názvů na základě správných podstatných jmen a spolu se všemi příslušnými citacemi.

Tato předvolba je obzvláště důležitá vzhledem k tomu, že některé použití řádných podstatných jmen bude vždy nutné – Q # následuje po sadě klasických jazyků, například a odkazuje na `Bool` typy v odkazu na logickou logiku, která je zase pojmenována za akceptovatelné. z logického typu Jiří.
Několik základních principů je obdobně pojmenováno podobným způsobem, včetně typu `Pauli` integrovaného do jazyka Q #.
Minimalizací použití řádných podstatných jmen, kde takové použití není nezbytné, snižujeme dopad na to, kde nelze rozumně obejít řádná podstatná jména.

# <a name="guidancetabguidance"></a>[Doprovodné materiály](#tab/guidance) 

Navrhujeme:

- Vyhněte se použití řádných podstatných jmen v názvech.

# <a name="examplestabexamples"></a>[Příklady](#tab/examples)

***

### <a name="type-conversions"></a>Převody typu ###

Vzhledem k tomu, že Q # je silně a staticky typovaného jazyka, hodnota jednoho typu může být použita pouze jako hodnota jiného typu pomocí explicitního volání funkce pro převod typu.
To je v kontrastu s jazyky, které umožňují hodnotám měnit typy implicitně (např.: povýšení typu) nebo prostřednictvím přetypování.
Výsledkem je, že funkce pro převod typu hrají důležitou roli ve vývoji knihovny Q # a sestávají z nich jedno z častých rozhodnutí o pojmenování.
Upozorňujeme však, že protože převody typu jsou vždycky _deterministické_, můžou být zapsány jako funkce a tak do výše uvedených rad.
Konkrétně doporučujeme, aby funkce pro převod typu neměly být nikdy pojmenovány jako slovesa (např.: `ConvertToX`) nebo příznakem příznaku příznaku (`ToX`), ale měly by se pojmenovat jako předpozice "adjektivum", které označují zdrojové a cílové typy (`XAsY`).
Při výpisu typů polí v názvech funkcí konverze typu doporučujeme zkrácený `Arr`.
Blokování výjimečných okolností, doporučujeme, aby všechny funkce pro převod typů byly pojmenovány pomocí `As`, aby je bylo možné rychle identifikovat.

# <a name="guidancetabguidance"></a>[Doprovodné materiály](#tab/guidance)

Navrhujeme:

- Pokud funkce převede hodnotu typu `X` na hodnotu typu `Y`, použijte buď název `AsY` nebo `XAsY`.

# <a name="examplestabexamples"></a>[Příklady](#tab/examples)

|   | Name (Název) | Popis |
|---|------|-------------|
| ☒ | <s>`ToDouble`</s> | Výsledkem předpozice "do" je příkazová fráze, která značí operaci a nikoli funkci. |
| ☒ | <s>`AsDouble`</s> | Typ vstupu není jasný od názvu funkce. |
| ☒ | <s>`PauliArrFromBoolArr`</s> | Vstupní a výstupní typy se zobrazí v nesprávném pořadí. |
| ☑ | `ResultArrAsBoolArr` | Vstupní typy i výstupní typy jsou jasné. |

***

### <a name="private-or-internal-names"></a>Privátní nebo interní názvy ###

V mnoha případech je název určený výhradně pro použití interního pro knihovnu nebo projekt a není zaručenou součástí rozhraní API nabízeného knihovnou.
Je vhodné jasně označit, že se jedná o případ, kdy se pojmenují funkce a operace, aby byly náhodné závislosti na kódu pouze v interním kódu.
Pokud operace nebo funkce není určena pro přímé použití, ale místo toho by měla být použita odpovídajícím voláním, které funguje na základě částečné aplikace, zvažte použití názvu začínajícího `_` pro volání, které je částečně použito.

# <a name="guidancetabguidance"></a>[Doprovodné materiály](#tab/guidance)

Navrhujeme:

- Není-li funkce, operace nebo uživatelsky definovaný typ součástí veřejného rozhraní API pro knihovnu nebo program Q #, ujistěte se, že název začíná počátečním podtržítkem (`_`).

# <a name="examplestabexamples"></a>[Příklady](#tab/examples)

|   | Name (Název) | Popis |
|---|------|-------------|
| ☒ | <s>`ApplyDecomposedOperation_`</s> | Podtržítko `_` nesmí být na konci názvu. |
| ☑ | `_ApplyDecomposedOperation` | Podtržítko `_` na začátku jasně označuje, že tato operace je určena pouze pro interní použití. |

***

### <a name="variants"></a>Typy ###

I když toto omezení nemusí být v budoucích verzích Q # trvalé, je v současné době v případě, že budou často skupiny souvisejících operací nebo funkcí, které jsou odlišené funktory jejich vstupy, nebo konkrétními typy jejich argumentů.
Tyto skupiny lze odlišit pomocí stejného kořenového názvu, následovaný jedním nebo dvěma písmeny, která označují jeho variantu.

| Auditování | Význam |
|--------|---------|
| `A` | Byl očekáván vstup, který podporuje `Adjoint` |
| `C` | Byl očekáván vstup, který podporuje `Controlled` |
| `CA` | Byl očekáván vstup, který podporuje `Controlled` a `Adjoint` |
| `I` | Vstup nebo vstupy jsou typu `Int` |
| `D` | Vstup nebo vstupy jsou typu `Double` |
| `L` | Vstup nebo vstupy jsou typu `BigInt` |

# <a name="guidancetabguidance"></a>[Doprovodné materiály](#tab/guidance)

Navrhujeme:

- Pokud funkce nebo operace nesouvisí s podobnými funkcemi nebo operacemi, které typy a funktor podporují jejich vstupy, nepoužívejte příponu.
- Pokud funkce nebo operace souvisí s podobnými funkcemi nebo operacemi podle typů a funktor podpory jejich vstupů, použijte přípony jako v tabulce výše, abyste rozlišili varianty.

# <a name="examplestabexamples"></a>[Příklady](#tab/examples)

***

### <a name="arguments-and-variables"></a>Argumenty a proměnné ###

Klíčový cíl kódu Q # pro funkci nebo operaci je, aby jej bylo možné snadno přečíst a pochopit.
Podobně názvy vstupů a argumentů typu by měly sdělit, jak se bude funkce nebo argument používat, jakmile bude k dispozici.


# <a name="guidancetabguidance"></a>[Doprovodné materiály](#tab/guidance)

Navrhujeme:

- Pro všechny proměnné a vstupní názvy použijte `pascalCase` v případě silné Předvolby na `CamelCase`, `snake_case`nebo `ANGRY_CASE`.
- Vstupní názvy by měly být popisné; Vyhněte se jednomu nebo dvěma názvům písmen, pokud je to možné.
- Operace a funkce, které přijímají přesně jeden argument typu, by měly poznamenat, že argument typu je `T`, když je jeho role zřejmá.
- Pokud funkce nebo operace přebírá více argumentů typu nebo pokud role jednoho argumentu typu není zřejmá, zvažte použití krátkého slova, které je `T` (např.: `TOutput`) pro každý typ.
- Do názvů argumentů a proměnných nezahrnujte názvy typů; Tyto informace můžou a by měly být poskytované vaším vývojovým prostředím.
- Zaznamenejte skalární typy podle jejich názvů literálů (`flagQubit`) a typy polí pomocí plural (`measResults`).
  V případě polí qubits je vhodné zvážit označení těchto typů pomocí `Register`, kde název odkazuje na sekvenci qubits, které úzce souvisejí s nějakým způsobem.
- Proměnné použité jako indexy do polí by měly začínat `idx` a měly by být jednotné (např.: `things[idxThing]`).
  Zejména se silně Vyhněte použití názvů proměnných s jedním písmenem jako indexů; Zvažte použití `idx` minimálně.
- Proměnné používané pro uchovávání délek polí by měly začínat `n` a měly by být v množném čísle (např.: `nThings`).

# <a name="examplestabexamples"></a>[Příklady](#tab/examples)

***

### <a name="user-defined-type-named-items"></a>Uživatelem definovaný typ s názvem Items ###

Pojmenované položky v uživatelsky definovaných typech by měly být pojmenovány jako `CamelCase`, a to i ve vstupu na konstruktory UDT.
To pomáhá při použití notace přistupujícího objektu (např.: `callable::Apply`) nebo zápisu typu Copy-and-Update (`set arr w/= Data <- newData`) jasně oddělit pojmenované položky od odkazů na místně vymezené proměnné.

# <a name="guidancetabguidance"></a>[Doprovodné materiály](#tab/guidance)

Navrhujeme:

- Pojmenované položky v konstruktorech UDT by měly být pojmenovány jako `CamelCase`; To znamená, že by měly začínat počátečními velkými písmeny.
- Pojmenované položky, které se překládají na operace, by měly být pojmenovány jako fáze operací.
- Pojmenované položky, které nelze přeložit na operace, by měly být pojmenovány jako podstatné fráze.
- Pro UDT, které zabalí operace, by měla být definována jedna pojmenovaná položka s názvem `Apply`.

# <a name="examplestabexamples"></a>[Příklady](#tab/examples)

|   | Zlomk | Popis |
|---|---------|-------------|
| ☑ | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | Název `Apply` je příkazová fráze ve formátu `CamelCase`, což naznačuje, že pojmenovaná položka je operace. |
| ☒ | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | Pojmenované položky by měly začínat počátečním velkým písmenem. |
| ☒ | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | Pojmenované položky, které se mají vyhodnotit na Functions, by měly být pojmenovány jako podstatné fráze, nikoli jako slovesová |

***

## <a name="input-conventions"></a>Vstupní konvence ##

Pokud vývojář volá operaci nebo funkci, je nutné určit různé vstupy pro tuto operaci nebo funkci v určitém pořadí, čímž se zvýší zátěžové zatížení, které vývojář vytvoří, aby mohli použít knihovnu.
Konkrétně úkol přeřazení vstupních objednávek je často z úlohy rušivý: programování implementace algoritmu pro plnění.
I když Rozsáhlá podpora integrovaného vývojového prostředí (IDE) může toto omezení zmírnit na velký rozsah, dobrý návrh a uplatnění běžných konvencí, může také pomoci minimalizovat zátěž vypracovanou rozhraním API.

Pokud je to možné, může být užitečné snížit počet vstupů očekávaných operací nebo funkcí, aby se role každého vstupu načetla okamžitě pro vývojáře, kteří volají tuto operaci nebo funkci, a vývojářům tento kód přečte později.
Zejména v případě, že není možné nebo rozumné snížit počet argumentů operace nebo funkce, je důležité mít konzistentní řazení, které minimalizuje neohlášení chyb uživatelů při předvídání pořadí vstupů.

Doporučujeme konvence pro řazení vstupu, které jsou převážně odvozené z úvahy částečné aplikace jako generalizace procesu curryfikace f (x, y) ≡ f (x) (y).
Proto by částečně použití prvních argumentů mělo být volat, které je užitečné, pokud je to vhodné.
Podle tohoto principu zvažte použití následujícího pořadí argumentů:

- Klasické nediskriminační argumenty, jako jsou úhly, vektory a atd.
- Argumenty pro možnost volat (funkce a argumenty).
  Pokud jsou funkce a operace provedeny jako argumenty, zvažte umístění operací po funkcích.
- Kolekce, na kterých se pracuje, pomocí volání argumentů podobným způsobem, jak `Map`, `Iter`, `Enumerate`a `Fold`.
- Argumenty qubit slouží jako ovládací prvky.
- Argumenty qubit slouží jako cíle.

Vezměte v úvahu operaci `ApplyPhaseEstimationIteration` pro použití ve odhadu fáze, který přebírá úhel a Oracle, předá úhel, který se `Rz` změnil řadou různých faktorů škálování, a pak řídí aplikace Oracle.
Vstupy jsme poznamenali `ApplyPhaseEstimationIteration` následujícím způsobem:

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
U některých funkcí a operací, které jsou ve zvláštních případech minimalizovány, napodobuje chování integrovaných funktory `Adjoint` a `Controlled`.
Například `ControlledOnInt<'T>` je typu `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, například, aby `ControlledOnInt<Qubit[]>(5, _)` fungovat jako `Controlled` funktor, ale na podmínku, kterou registr ovládacího prvku představuje stav $ \ket{5} = \ket{101}$.
Proto vývojář očekává, že vstupy `ControlledOnInt` umístit vracené operace jako poslední a že výsledná operace přebírá jako svůj vstupní `(Qubit[], 'T)`---stejné pořadí, jako následuje výstup `Controlled` funktor.

# <a name="guidancetabguidance"></a>[Doprovodné materiály](#tab/guidance)

Navrhujeme:

- Používejte vstupní pořadí konzistentní s použitím částečné aplikace.
- Používejte vstupní pořadí konzistentní s integrovanými funktory.
- Všechny klasické vstupy umístěte před všechny vstupy za sebou.

# <a name="examplestabexamples"></a>[Příklady](#tab/examples)

***

## <a name="documentation-conventions"></a>Konvence dokumentace ##

Jazyk Q # umožňuje připojit dokumentaci k operacím, funkcím a uživatelsky definovaným typům pomocí speciálně formátovaných dokumentačních komentářů.
Tyto komentáře k této dokumentaci jsou označeny trojitými lomítky (`///`), [](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) které se dají použít k popisu účelu jednotlivých operací, funkcí a uživatelsky definovaných typů, které vstupy očekává a tak dále.
Kompilátor, který je součástí vývojové sady pro všechna ta, extrahuje tyto komentáře a použije je k tomu https://docs.microsoft.com/quantum, aby vám pomohly sázení dokumentaci podobnou dokumentaci.
Podobně jazykový Server, který je součástí vývojové sady pro plnění, používá tyto komentáře k poskytnutí pomocníka uživatelům při přechodu myší na symboly v kódu Q #.
Používání dokumentačních komentářů tak může pomoci uživatelům vydávat smysl kódu tím, že poskytuje užitečnou referenci pro podrobnosti, které nejsou snadno vyjádřeny pomocí dalších úmluv v tomto dokumentu.

<div class="nextstepaction">
    [Referenční dokumentace k syntaxi komentářů k dokumentaci](xref:microsoft.quantum.language.statements#documentation-comments)
</div>

Aby bylo možné efektivně využít tuto funkci, doporučujeme, abyste při psaní dokumentačních komentářů měli na paměti pár věcí.

# <a name="guidancetabguidance"></a>[Doprovodné materiály](#tab/guidance)

Navrhujeme:

- Každá veřejná funkce, operace a uživatelsky definované typy by měly hned předcházet dokumentační komentář.
- Každý dokumentační komentář by měl mít minimálně následující oddíly:
    - Souhrn
    - Vstup
    - Výstup (Pokud je k dispozici)
- Ujistěte se, že všechny souhrny jsou dvě nebo méně vět. Pokud je potřeba více místa, poskytněte `# Description` oddíl hned za `# Summary` s úplnými podrobnostmi.
- Tam, kde je to rozumné, nezahrnuje matematiku v souhrnech, protože ne všichni klienti podporují TeX Notation v souhrnech. Pamatujte na to, že při psaní dokumentů prose (např. TeX nebo Markdownu) může být vhodnější použít delší délky řádků.
- Poskytněte všechny relevantní matematické výrazy v části `# Description`.
- Při popisu vstupů neopakuje typ každého vstupu, protože je možné ho odvodit kompilátorem a riziko zavedení nekonzistence.
- Poskytněte příklady podle potřeby, každý v jejich `# Example` oddíl.
- Stručně popište každý příklad před výpisem kódu.
- Seznamte se se všemi relevantními školními publikacemi (například dokumenty, postupy, příspěvky na blogu a alternativní implementace) v části `# References` jako seznam odkazů s odrážkami.
- Ujistěte se, že pokud je to možné, všechny odkazy na citace jsou trvalé a neměnné identifikátory (DOIs nebo arXiv čísla se správou verzí).
- Pokud je operace nebo funkce v souvislosti s jinými operacemi nebo funkcemi podle funktor variant, vypíše další varianty jako odrážky v části `# See Also`.
- Ponechte prázdný řádek komentáře mezi oddíly úrovně 1 (`/// #`), ale nenechávejte prázdné řádky mezi oddíly úrovně 2 (`/// ##`).

# <a name="examplestabexamples"></a>[Příklady](#tab/examples)

#### <a name=""></a>☑ ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a>Konvence formátování ##

Kromě výše uvedených návrhů je užitečné pomoct, aby byl kód co čitelný, aby bylo možné použít konzistentní pravidla formátování.
Taková pravidla formátování podle povahy mají za následek trochu libovolné a silně silné až do osobních estetických.
Nicméně doporučujeme, abyste zachovali konzistentní sadu formátovacích konvencí v rámci skupiny spolupracovníky a zejména u rozsáhlých projektů Q #, jako je například vývojová sada.
Tato pravidla lze automaticky použít pomocí nástroje formátování integrovaného s kompilátorem Q #.

# <a name="guidancetabguidance"></a>[Doprovodné materiály](#tab/guidance) 

Navrhujeme:

- Místo karet pro přenositelnost použijte čtyři mezery.
  V VS Code například:
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- Zalomení řádku na 79 znaků, kde je to přijatelné.
- Používejte mezery kolem binárních operátorů.
- Používejte mezery na kterékoli straně dvojtečky používané pro anotace typu.
- Použijte jednu mezeru za čárkami použitou v poli a literálech řazené kolekce členů (např.: ve vstupech až po funkce a operace).
- Nepoužívejte mezery za název funkce, operace nebo UDT ani po `@` v deklaracích atributů.
- Každá deklarace atributu by měla být na samostatném řádku.

# <a name="examplestabexamples"></a>[Příklady](#tab/examples)

|   | Zlomk | Popis |
|---|---------|-------------|
| ☒ | <s>`2+3`</s> | Používejte mezery kolem binárních operátorů. |
| ☒ | <s>`target:Qubit`</s> | Používejte mezery kolem dvojtečky typu anotace. |
| ☑ | `Example(a, b, c)` | Položky ve vstupní řazené kolekci členů jsou pro čitelnosti správně rozmístěny. |
| ☒ | <s>`Example (a, b, c)`</s> | Mezery by měly být potlačeny za názvy funkcí, operací nebo UDT. |

***

