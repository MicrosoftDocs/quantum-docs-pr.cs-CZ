---
title: 'Principy návrhu rozhraní API Q #'
description: 'Principy návrhu rozhraní API Q #'
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
ms.openlocfilehash: def6a9f12accfa399fd4db3783b9899fc743f025
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274551"
---
# <a name="q-api-design-principles"></a>Principy návrhu rozhraní API Q #

## <a name="introduction"></a>Úvod

Jako jazyk a jako platforma verze Q # umožňuje uživatelům psát, spouštět, rozumět a zkoumat aplikace v neprovozu.
Aby bylo možné uživatele při návrhu knihoven Q # přizpůsobovat, pořiďte si sadu principů návrhu rozhraní API, které vám pomůžou navrhnout naše návrhy a pomoct nám využít použitelné knihovny pro komunita pro vývoj po částech.
Tento článek obsahuje seznam těchto principů a obsahuje příklady, které vám pomohou při navrhování rozhraní API Q #.

> [!TIP]
> Toto je poměrně podrobný dokument, který je určený k tomu, aby usnadnil vývoj knihovny a podrobné příspěvky knihoven.
> Je pravděpodobné, že je to nejužitečnější, pokud píšete vlastní knihovny v Q # nebo pokud přispíváte do [úložiště knihovny Q #](https://github.com/microsoft/QuantumLibraries)větší funkce.
>
> Na druhé straně, pokud se naučíte, jak přispívat do vývojové sady pro práci s více společnostmi obecně, doporučujeme začít s [průvodcem pro příspěvky](xref:microsoft.quantum.contributing).
> Pokud hledáte obecnější informace o tom, jak doporučujeme naformátovat kód Q #, může vás zajímat [Průvodce stylem](xref:microsoft.quantum.contributing.style).

## <a name="general-principles"></a>Obecné zásady

**Princip klíče:** Zveřejňujte rozhraní API, která umístí fokus na aplikace.

- ✅**Vyberte název** operace a funkce, který odráží strukturu algoritmů a aplikací vysoké úrovně.
- ⛔️ **DON'T** nezveřejňujte rozhraní API, která se zaměřují hlavně na podrobnosti implementace nízké úrovně.

**Princip klíče:** Spusťte jednotlivé návrhy rozhraní API s použitím ukázkových případů použití, abyste zajistili, že je rozhraní API intuitivní.

- ✅**Zajistěte, aby každá** součást veřejného rozhraní API měla odpovídající případ použití, nikoli pokusit se navrhovat všechna možná použití od začátku.
    Nepoužívejte jiné, nezaveďte veřejná rozhraní API pro případ, že jsou užitečná, ale ujistěte se, že každá část rozhraní API má *konkrétní* příklad, ve kterém bude užitečná.

  *4.6*
  - @"microsoft.quantum.canon.applytoeachca"dá se použít jako `ApplyToEachCA(H, _)` pro přípravu registrů v jednotném stavu, což je běžný úkol v mnoha algoritmech pro každé z nich. Stejnou operaci lze také použít pro mnoho dalších úloh v rámci přípravy, čísel a algoritmů založených na Oracle.

- ✅Nové návrhy rozhraní API pro **pracovní debatu** a workshop vám umožní dvakrát ověřit, jestli jsou intuitivní a splňují navržené případy použití.

  *4.6*
  - Zkontrolujte aktuální kód Q a \# Zjistěte, jak by nové návrhy rozhraní API mohly zjednodušit a objasnit stávající implementace.
  - Projděte si návrhy navržených rozhraní API se zástupci primárních cílových skupin.

**Princip klíče:** Navrhněte rozhraní API pro podporu a podporu čitelného kódu.

- ✅**Zajistěte, aby byl** kód čitelný odborníky v doméně a znalci bez expertů.
- ✅**DO** Zaměřte se na účinky jednotlivých operací a funkcí v rámci algoritmu vysoké úrovně, a to pomocí dokumentace, která bude v případě potřeby podrobná v podrobnostech implementace.
- ✅Pokaždé, když **je to možné, postupujte podle** návodu pro běžný [ \# styl Q](xref:microsoft.quantum.contributing.style) .

**Princip klíče:** Navrhněte rozhraní API, aby byly stabilní a poskytovaly dopředné kompatibility.

- ✅Když **se vyžadují zásadní** změny, neúčtují stará rozhraní API korektně.

- ✅**Poskytněte operace** "Shim" a funkce, které umožňují správné fungování stávajícího uživatelského kódu během vyřazení.

  *4.6*
  - Při přejmenování operace, která je volána `EstimateExpectation` na `EstimateAverage` , zaveďte novou operaci `EstimateExpectation` s názvem, která volá původní operaci na svém novém názvu, aby existující kód mohl nadále fungovat správně.

- ✅**Použijte** @"microsoft.quantum.core.deprecated" atribut pro komunikaci nepoužívaných uživatelů.

- ✅Při přejmenování operace nebo **funkce zadejte nový** název jako vstup řetězce do `@Deprecated` .

- pro podporované verze **se ⛔️ neodstraňují** stávající funkce ani operace, aniž by byla doba zastaralosti aspoň šest měsíců pro verze Preview nebo aspoň dva roky.

## <a name="functions-and-operations"></a>Funkce a operace

**Klíčový princip:** Ujistěte se, že všechny funkce a operace mají v rámci rozhraní API jeden dobře definovaný účel.

- ⛔️ **DON'T** nezveřejňujte funkce a operace, které provádějí více nesouvisejících úloh.

**Klíčový princip:** návrh funkcí a operací, které se mají co možná nejvíce použít, a pro předvídání budoucích potřeb.

- ✅**Udělejte** návrh funkcí a operací, abyste mohli dobře začínat dalšími funkcemi a operacemi ve stejném rozhraní API i v dříve existujících knihovnách.

  *4.6*
  - @"microsoft.quantum.canon.delay"Operace vytváří minimální předpoklady o jeho vstupu, takže se dá použít ke zpoždění aplikací obou operací napříč standardní knihovnou Q # nebo definovanými uživateli.
    <!-- TODO: define bad example. -->

- ✅**Vystavte** čistě deterministické klasický Logic jako funkce namísto operací.

  *4.6*
  - Podprogram, který má čtverce vstupu s plovoucí desetinnou čárkou, se dá napsat deterministickému, takže by měl být uživateli vystaven jako `Squared : Double -> Double` místo operace `Square : Double => Double` . To umožňuje, aby podrutina byla volána na více místech (například uvnitř jiných funkcí) a poskytovala užitečné informace o optimalizaci kompilátoru, který může ovlivnit výkon a optimalizace.
  - `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]`a `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` liší se zárukami provedenými v souvislosti s determinismem; obě jsou užitečné v různých případech.
  - Rutiny rozhraní API, které transformují použití operací s více poli, je často možné provádět deterministickým způsobem, takže je možné je zpřístupnit jako funkce, jako je `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)` .

- ✅**Proveďte** generalizaci vstupního typu tak, jak je to pro každou funkci a operaci přijatelné, podle potřeby pomocí parametrů typu.

  *4.6*
  - `ApplyToEach`má typ `<'T>(('T => Unit), 'T[]) => Unit` místo konkrétního typu nejběžnější aplikace, `((Qubit => Unit), Qubit[]) => Unit` .

> [!TIP]
> Je důležité, abyste předpokládali budoucí potřeby, ale je také důležité řešit konkrétní problémy pro uživatele.
> Na základě tohoto klíčového principu vždy vyžaduje pečlivé zvážení a vyrovnávání, aby nedocházelo k vývoji rozhraní API "jenom v případě".

**Princip klíče:** vyberte vstupní a výstupní typy pro funkce a operace, které jsou předvídatelné a které komunikují účel, který je možné volat.

- ✅**Použijte typy** řazené kolekce členů k logickému seskupení vstupů a výstupů, které jsou významné pouze při zvážení. V těchto případech zvažte použití uživatelsky definovaného typu.

  *4.6*
  - Funkce pro výstup místního minima jiné funkce může být potřeba přebírat meze intervalu hledání jako vstup, což `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` může být vhodný podpis.
  - Operace pro odhad odvozeného objektu třídění strojového učení pomocí metody posunu parametru může vyžadovat, aby se jako vstupy převzaly vektorové a neposunuté parametry. `(unshifted : Double[], shifted : Double[])`V tomto případě může být vhodný vstup podobný tomuto.

- ✅**Seřazení položek** ve vstupních a výstupních řazených kolekcích členů konzistentně napříč různými funkcemi a operacemi.

  *4.6*
  - Při zvažování dvou nebo funkcí nebo operací, které každý z nich přebírají úhel otočení a cílový qubit jako vstup, se ujistěte, že jsou seřazené stejně v každé vstupní řazené kolekci členů. To znamená, preferovat `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` a `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` a `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` .

**Klíčový princip:** návrh funkcí a operací pro správnou spolupráci s funkcemi jazyka Q, jako \# je například částečná aplikace.

- ✅**Seřazení položek** ve vstupních řazených kolekcích členů tak, aby nejčastěji používané vstupy probíhaly jako první (tj.: tak, aby částečné aplikace fungují podobně jako procesu curryfikace).

  *4.6*
  - Operace `ApplyRotation` , která přebírá číslo s plovoucí desetinnou čárkou a qubit, může být často částečně aplikována se vstupem s plovoucí desetinnou čárkou pro použití s operacemi, které očekávají zadání typu `Qubit => Unit` . Proto signatura`operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`
      bude fungovat konzistentně s částečnou aplikací.
  - Obvykle tento návod znamená umístění všech klasických dat před všemi qubits ve vstupních řazených kolekcích členů, ale má dobré rozhodnutí a kontroluje, jak se rozhraní API volá v praxi.

## <a name="user-defined-types"></a>Uživatelsky definované typy

**Klíčový princip:** použití uživatelsky definovaných typů, které usnadňují použití rozhraní API pro lepší a pohodlné používání.

- ✅**Zaveďte nové** uživatelsky definované typy a poskytněte tak užitečné zkratky pro dlouhé a/nebo komplikované typy.

  *4.6*
  - V případech, kdy typ operace se třemi vstupy qubit pole se obvykle považuje za vstup nebo vrácený jako výstup, který poskytuje UDT jako`newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`
      vám může pomoct zajistit užitečnou zkrácený tvar.

- ✅Zaveďte nové uživatelsky definované typy k **označení toho,** že daný základní typ by měl být použit pouze v velmi konkrétním smyslu.

  *4.6*
  - Operace, která by měla být interpretována speciálně jako operace, která kóduje klasická data do registru, může být vhodná pro označení uživatelem definovaným typem `newtype InputEncoder = (Apply : (Qubit[] => Unit))` .

- ✅**Zaveďte nové** uživatelsky definované typy pomocí pojmenovaných položek, které umožňují budoucí rozšíření (např.: strukturu výsledků, která může v budoucnu obsahovat další pojmenované položky).

  *4.6*
  - Když operace `TrainModel` zveřejňuje velký počet možností konfigurace, vystavení těchto možností jako nového `TrainingOptions` UDT a zadání nové funkce `DefaultTrainingOptions : Unit -> TrainingOptions` umožní uživatelům přepsat konkrétní pojmenované položky v TRAININGOPTIONS hodnotách UDT a zároveň umožnit vývojářům knihovny PŘIDÁVAT nové položky UDT podle potřeby.

- ✅**Deklarujte** pojmenované položky pro nové uživatelsky definované typy v předvolbách, aby vyžadovaly, aby uživatelé znali správné rozstavbu řazené kolekce členů.

  *4.6*
  - Když představuje komplexní číslo v jeho polárním rozkladu, dávají přednost `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` `newtype ComplexPolar = (Double, Double)` .

**Klíčový princip:** použití uživatelsky definovaných typů způsobem, jak omezit zátěžové zatížení a které nevyžadují, aby se uživatel dozvěděl o dalších konceptech a nomenklatuře.

- ⛔️ **DON'T** nezavádí uživatelsky definované typy, které vyžadují, aby uživatel mohl často používat operátor rozbalení ( `!` ), nebo který obvykle vyžaduje více úrovní rozbalení. Mezi možné strategie zmírňování patří:

  - Při vystavení uživatelsky definovaného typu s jednou položkou zvažte definování názvu pro tuto položku. Zvažte například `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` v Předvolby na `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)` .

  - Zajištění, že jiné funkce a operace mohou přijímat "zabalené" instance UDT přímo.

- ⛔️ **DON'T** nezavádět nové uživatelsky definované typy, které duplikují předdefinované typy bez poskytnutí dalších expresivity.

  *4.6*
  - UDT `newtype QubitRegister = Qubit[]` neposkytuje žádné další expresivity nad `Qubit[]` a je proto těžší ho použít bez discernable výhody.
  - UDT `newtype LittleEndian = Qubit[]` popisuje, jak se má použít a interpretovat základní registr, a poskytuje tak další expresivity nad svým základním typem.

- ⛔️ nezavádět funkce přistupujícího objektu, **Pokud není potřeba** striktně;   v tomto případě silně preferovat pojmenované položky.

  *4.6*
  - Při seznámení s `newtype Complex = (Double, Double)` rozhraním UDT preferovat změnu definice na `newtype Complex = (Real : Double, Imag : Double)` k představení funkcí `GetReal : Complex -> Double` a `GetImag : Complex -> Double` .

## <a name="namespaces-and-organization"></a>Obory názvů a organizace

**Klíčový princip:** vyberte názvy oborů názvů, které jsou předvídatelné a které jasně sdělují účel funkcí, operací a uživatelsky definovaných typů v jednotlivých oborech názvů.

- ✅**Jmenujte obory názvů jako** `Publisher.Product.DomainArea` .

  *4.6*
  - Funkce, operace a UDT publikované Microsoftem jako součást funkce simulace doby provozu v rámci prostředí pro vývoj provozu po částech se nacházejí v `Microsoft.Quantum.Simulation` oboru názvů.
  - `Microsoft.Quantum.Math`představuje obor názvů publikovaný společností Microsoft jako součást prostředí pro vývoj všech stavů, které se týká matematické oblasti domény.

- ✅**Založte operace** , funkce a uživatelsky definované typy, které se používají pro konkrétní funkce, do oboru názvů, který popisuje tyto funkce, a to i v případě, že se tato funkce používá v různých doménách problému.

  *4.6*
  - Rozhraní API pro přípravu stavu publikovaná Microsoftem jako součást vývojové sady pro všechna ta budou umístěna do `Microsoft.Quantum.Preparation` .
  - Rozhraní API pro simulaci nedostatku doby publikovaná společností Microsoft jako součást vývojové sady pro plnění do více částí budou umístěna do `Microsoft.Quantum.Simulation` .

- ✅**Založte operace** , funkce a uživatelsky definované typy používané pouze v rámci konkrétních domén do oborů názvů, které označují jejich doménu nástroje. V případě potřeby použijte podobory názvů k označení úkolů s fokusem v rámci každého oboru názvů specifického pro doménu.

  *4.6*
  - Služba Machine Learning, která je publikovaná společností Microsoft, je v podstatě umístěna do @"microsoft.quantum.machinelearning" oboru názvů, ale ukázkové datové sady jsou poskytovány @"microsoft.quantum.machinelearning.datasets" oborem názvů.
  - Množství pro každé z nich stanoví rozhraní API, která jsou publikovaná Microsoftem jako součást vývojové sady pro všechna využívání `Microsoft.Quantum.Chemistry` . Funkce specifické pro implementaci Wigneru na úrovni Jordánska se můžou umístit do `Microsoft.Quantum.Chemistry.JordanWigner` , takže primární rozhraní pro chemii stavové oblasti v doméně se netýká implementací.

**Princip klíče:** K úmyslnému využití plochy rozhraní API uživatelům a ke skrytí vnitřních podrobností souvisejících s implementací a testováním vašich rozhraní API používejte modifikátory oborů názvů a přístupu.

- ✅Kdykoli **je to vhodné, umístěte všechny** funkce a operace potřebné k implementaci rozhraní API do stejného oboru názvů, jako je implementované rozhraní API, ale označená "soukromá" nebo "interní" klíčová slova, která označují, že nejsou součástí veřejného prostoru rozhraní API pro knihovnu. Použijte název začínající podtržítkem ( `_` ) k vizuálnímu odlišení privátních a interních operací a funkcí od veřejných volat.

  *4.6*
  - Název operace `_Features` označuje funkci, která je soukromá pro daný obor názvů a sestavení a měla by být doprovázena `internal` klíčovým slovem.

- ✅V případě, že je k implementaci rozhraní API pro daný obor názvů potřeba použít rozsáhlou sadu privátních funkcí nebo operací, **umístěte je** do nového oboru názvů, který odpovídá implementovanému oboru názvů a končí `.Private` .

- ✅Všechny testy **jednotek umístěte do** oborů názvů, které odpovídají oboru názvů pod testem a končí `.Tests` .

## <a name="naming-conventions-and-vocabulary"></a>Konvence pojmenování a slovník

**Princip klíče:** Vyberte názvy a terminologii, které jsou jasné, přístupné a čitelné v rámci nejrůznějších cílových skupin, včetně toho, co se jedná i o odborníky.

- ⛔️ **nepoužívejte diskriminační** nebo vyloučení názvů identifikátorů, ani terminologie v dokumentaci k dokumentaci k rozhraní API.

- ✅**Použijte komentáře** k dokumentaci k rozhraní API k poskytnutí relevantního kontextu, příkladů a odkazů, zejména pro obtížnější koncepty.

- ⛔️ **DON'T** Nepoužívejte názvy identifikátorů, které jsou zbytečně esoteričtějším nebo které vyžadují významné znalosti algoritmů pro čtení.

  *4.6*
  - Preferovat "iteraci zesílení amplitud" na "Grover iterace"

- ✅**Vyberte operace** a názvy funkcí, které jasně sdělují zamýšlený účinek, který lze volat, a nikoli jeho implementaci. Všimněte si, že implementace může a měla by se zdokumentovat v [dokumentaci k dokumentaci k rozhraní API](xref:microsoft.quantum.guide.filestructure#documentation-comments).

  *4.6*
  - Preferovat "odhad překrytí" na "Hadamard test", protože ten pak komunikuje s implementací bývalého.

- ✅**Používejte slova** konzistentním způsobem napříč všemi \# rozhraními API Q:

  - **Příkazy**

    - **Assert**: Ověřte, jestli předpoklad týkající se stavu cílového počítače a jeho qubits obsahuje, možná pomocí nefyzických prostředků. Operace používající tuto operaci by měly být vždy bezpečně vyměnitelná bez vlivu na funkce knihoven a spustitelných programů. Všimněte si, že na rozdíl od skutečností můžou kontrolní výrazy obecně záviset na externím stavu, jako je například stav registru qubit, spouštěcí prostředí nebo tak dále. Protože závislost na externím stavu je druh vedlejšího účinku, kontrolní výrazy musí být vystavené jako operace, nikoli funkce.

    - **Odhad**: použití jednoho nebo více možných opakovaných měření, odhadem klasického množství z výsledků měření.

      *4.6*
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - **Příprava**: použití operace nebo posloupnosti operací na jeden nebo více qubits předpokládá, že se spustí v konkrétním počátečním stavu (obvykle $ \ket{00\cdots 0} $), což způsobí, že se stav těchto qubits bude vyvíjet do požadovaného koncového stavu. Obecně platí, že v případě jiných států, než je zadaný počáteční stav, **může** dojít k nedefinované jednotkové transformaci, ale **je třeba** zachovat tuto operaci a její sousední akci "zrušit výstup" a použít možnost No-op.

      *4.6*
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - **Measure**: použijte operaci nebo sekvenci operací na jeden nebo více qubits a přečtěte si klasická data zpět.

      *4.6*
      - @"microsoft.quantum.intrinsic.measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - **Apply**: použijte operaci nebo sekvenci operací na jeden nebo více qubits, což způsobí, že se stav těchto qubits mění souvislým způsobem. Tato operace je nejobecnější sloveso v \# nomenklatuře Q a **neměla by být** použita, pokud je konkrétnější příkaz přímo relevantní.

  - **Podstatná jména**:

    - **Fakt**: logická podmínka, která závisí jenom na svých vstupech, a ne na stavu cílového počítače, jeho prostředí nebo stavu qubits počítače. Na rozdíl od kontrolního výrazu je fakt jenom citlivý na *hodnoty* , které jsou pro tuto skutečnost k dispozici. Příklad:

      *4.6*
      - @"microsoft.quantum.diagnostics.equalityfacti": představuje fakt rovnosti o dvou celočíselných vstupech; celá čísla zadaná jako vstup jsou rovna sobě navzájem, nebo nejsou závislá na jakémkoli jiném stavu programu.

    - **Možnosti:** Typ UDT obsahující několik pojmenovaných položek, které mohou sloužit jako nepovinné argumenty pro funkci nebo operaci. Příklad:

      *4.6*
      - @"microsoft.quantum.machinelearning.trainingoptions"Parametr UDT zahrnuje pojmenované položky pro studijní kurzy, velikost minibatch a další konfigurovatelné parametry pro školení ml.

  - **Přídavná jména**:

    - ⛔️ **novinka**: Tento adjektivum by se neměl používat, protože se **nemusíte** používat jako sloveso v řadě programovacích jazyků (například C++, C#, Java, TypeScript, PowerShell).

  - **Předpozice:** V některých případech je možné použít předpozice k dalšímu jednoznačnému nebo objasnění rolí podstatných jmen a operací v názvech funkcí a operací. K tomu by se mělo dbát opatrně a konzistentně, ale

    - **Jako:** Představuje, že vstup a výstup funkce funkce představují stejné informace, ale výstup představuje tyto informace **jako** *X* namísto původní reprezentace. To je zvláště běžné pro funkce pro převod typů.

      *4.6*
      - `IntAsDouble(2)`označuje, že vstup ( `2` ) i výstup ( `2.0` ) reprezentují stejné informace, ale používají k tomu různé \# typy dat Q.

    - **Od:** Aby se zajistila konzistence, tato předpozice **by se neměla** používat k označení funkcí pro převod typu nebo jakéhokoli jiného případu **, pokud je to vhodné** .

    - ⛔️ **na:** tato Předpozice **by se neměla** používat, protože se vyhnete nejasnostem při použití jako operace v mnoha programovacích jazycích.
