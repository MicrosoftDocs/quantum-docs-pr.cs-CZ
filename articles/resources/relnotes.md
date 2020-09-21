---
title: Poznámky k verzi sady Quantum Development Kit
description: Přečtěte si o nejnovějších aktualizacích sady Microsoft Quantum Development Kit ve verzi Preview.
author: bradben
ms.author: v-benbra
ms.date: 8/30/2020
ms.topic: article
uid: microsoft.quantum.relnotes
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5036b4d401bb775a7fee2252ca26e7725bc19004
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834138"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a>Poznámky k verzi sady Quantum Development Kit

Tento článek obsahuje informace o jednotlivých vydáních sady Quantum Development Kit.

Pokyny k instalaci najdete v [příručce pro instalaci](xref:microsoft.quantum.install).

Pokyny k aktualizaci najdete v [příručce pro aktualizaci](xref:microsoft.quantum.update).

## <a name="version-01220082513"></a>0.12.20082513 verze

*Datum vydání: 25. srpna 2020*

Tato verze obsahuje následující:

- Nový [obor názvů Microsoft... Random](xref:microsoft.quantum.random)nabízí pohodlnější způsob, jak v rámci programů vzorkovat náhodné hodnoty Q# . ([QuantumLibraries # 311](https://github.com/microsoft/QuantumLibraries/pull/311), [qsharp-runtime # 328](https://github.com/microsoft/qsharp-runtime/pull/328))
- Byl vylepšen [obor názvů Microsoft. NázevOperace. Diagnostics](xref:microsoft.quantum.diagnostics) s novou [ `DumpOperation` operací](xref:microsoft.quantum.diagnostics.dumpoperation)a nové operace pro omezení přidělení qubit a volání Oracle. ([QuantumLibraries # 302](https://github.com/microsoft/QuantumLibraries/pull/302))
- Nový [ `%project` příkaz Magic](xref:microsoft.quantum.iqsharp.magic-ref.project) v jazyce Q# Python a [ `qsharp.projects` rozhraní API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) v Pythonu pro podporu odkazů na Q# projekty mimo aktuální složku pracovního prostoru. Aktuální omezení této funkce naleznete v tématu [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) . 
- Podpora pro automatické načítání `.csproj` souborů pro I Q# hostitele/Python, které umožňují načtení externích projektů nebo odkazů na balíčky v době inicializace. Další podrobnosti najdete v příručce pro použití [ Q# s poznámkovým blokům Python a Jupyter](xref:microsoft.quantum.guide.host-programs) .
- Byl přidán vzorek ErrorCorrection. Syndrome.
- Přidání propojení přizpůsobitelné k SimpleIsing.
- Ukázka HiddenShift se aktualizovala.
- Přidání ukázky pro řešení Sudoku s algoritmem Grover (externí příspěvek)
- Obecné opravy chyb.

Podívejte se na úplný seznam uzavřených PR pro [knihovny](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilátor](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [modul runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ukázky](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [i Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) a [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01220072031"></a>0.12.20072031 verze

*Datum vydání: od 21. července 2020*

Tato verze obsahuje následující:

- Otevřené obory názvů v Q# poznámkových blocích jsou nyní k dispozici pro všechny budoucí výpočty buněk. To umožňuje například, aby se obory názvů otevíraly jednou v buňce v horní části poznámkového bloku místo nutnosti otevírat relevantní obory názvů v každé buňce kódu. Nový `%lsopen` příkaz Magic zobrazí seznam aktuálně otevřených oborů názvů.

Podívejte se na úplný seznam uzavřených PR pro [knihovny](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilátor](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [modul runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ukázky](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [i Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) a [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01220070124"></a>0.12.20070124 verze

*Datum vydání: 2. července 2020*

Tato verze obsahuje následující:

- Nový `qdk-chem` Nástroj pro převod formátů serializace ve starších verzích elektronické struktury (např.: FCIDUMP) do [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)
- Nové funkce a operace v [`Microsoft.Quantum.Synthesis`](xref:microsoft.quantum.synthesis) oboru názvů pro soudržné používání klasických Oracle pomocí transformačních a dekompozicí založených algoritmů syntézy.
- Q#Nyní povolujem argumenty pro `%simulate` příkazy, `%estimate` a další Magic. Další podrobnosti najdete v referenčních informacích k [ `%simulate` příkazu Magic](xref:microsoft.quantum.iqsharp.magic-ref.simulate) .
- Nové možnosti zobrazení fáze Q# v I Další podrobnosti najdete v referenčních informacích k [ `%config` příkazu Magic](xref:microsoft.quantum.iqsharp.magic-ref.config) .
- I Q# a `qsharp` balíček Pythonu jsou teď k dispozici prostřednictvím balíčků conda ([qsharp](https://anaconda.org/quantum-engineering/qsharp) a [iqsharp](https://anaconda.org/quantum-engineering/iqsharp)), aby se zjednodušila místní instalace Q# funkcí Jupyter a Pythonu do conda prostředí. Další podrobnosti najdete v [ Q# poznámkových blocích Jupyter](xref:microsoft.quantum.install.jupyter) a v Průvodci instalací [ Q# Pythonu](xref:microsoft.quantum.install.python) .
- Při použití simulátoru už qubits není potřeba ve stavu | 0 ⟩ po vydaných verzích, ale dá se automaticky resetovat, pokud se naměřeny bezprostředně před vydáním.
- Aktualizace, které usnadňují Q# uživatelům využívání balíčků knihoven s různými VERZEMI QDK a vyžadují jenom hlavní čísla & menší verze, nikoli jenom přesnou stejnou verzi
- Odebraný nepoužívaný `Microsoft.Quantum.Primitive.*` obor názvů
- Přesunuté operace:
  - `Microsoft.Quantum.Intrinsic.Assert` je teď `Microsoft.Quantum.Diagnostics.AssertMeasurement`
  - `Microsoft.Quantum.Intrinsic.AssertProb` je teď `Microsoft.Quantum.Diagnostics.AssertMeasurementProbability`
- Opravy chyb 

Podívejte se na úplný seznam uzavřených PR pro [knihovny](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilátor](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [modul runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ukázky](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [i Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) a [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-0112006403"></a>Verze 0.11.2006.403

*Datum vydání: 4. června 2020*

Tato verze opravuje chybu ovlivňující kompilaci Q# projektů.

## <a name="version-0112006207"></a>Verze 0.11.2006.207

*Datum vydání: 3. června 2020*

Tato verze obsahuje následující:

- Q# poznámkové bloky a hostitelské programy Pythonu už nebudou úspěšné, když Q# je přítomen vstupní bod.
- Aktualizace [standardní knihovny](xref:microsoft.quantum.libraries.standard.intro) pro použití modifikátorů přístupu
- Kompilátor teď povoluje modul plug-in pro kroky přepsání mezi vestavěnými kroky přepsání.
- V souladu s plánem popsaným v našich [principech rozhraní API](xref:microsoft.quantum.contributing.api-design) bylo odebráno několik vyřazených funkcí a operací. Q# programy a knihovny, které sestavují bez upozornění ve verzi 0.11.2004.2825, budou i nadále fungovat beze změny.

Podívejte se na úplný seznam uzavřených PR pro [knihovny](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilátor](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [modul runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ukázky](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [i Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) a [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

> [!NOTE]
> Tato verze obsahuje chybu ovlivňující kompilaci Q# projektů. Doporučujeme upgradovat na novější verzi.

## <a name="version-01120042825"></a>Verze 0.11.2004.2825

*Datum vydání: 30. dubna 2020*

Tato verze obsahuje následující:

- Nová podpora pro Q# aplikace, která už nevyžadují hostitelský soubor C# nebo Python. Další informace o tom, jak začít s Q# aplikacemi, najdete [tady](xref:microsoft.quantum.install.standalone).
- Aktualizovali jsme rychlý start generátoru náhodných čísel, takže už nevyžaduje hostitelský soubor v C# nebo Pythonu. Podívejte se na aktualizovaný [Rychlý start](xref:microsoft.quantum.quickstarts.qrng).
- Vylepšení výkonu Q# Docker images

> [!NOTE]
> Q# aplikace používající nový [`@EntryPoint()`](xref:microsoft.quantum.core.entrypoint) atribut se aktuálně nedají volat z hostitelských programů Pythonu nebo .NET.
> Další informace najdete v tématech týkajících se [Pythonu](xref:microsoft.quantum.install.python) a [interoperability rozhraní .NET](xref:microsoft.quantum.install.cs).

## <a name="version-01120033107"></a>Verze 0.11.2003.3107

*Datum vydání: 31. března 2020*

Toto vydání obsahuje menší opravy chyb pro verzi 0.11.2003.2506.

## <a name="version-01120032506"></a>Verze 0.11.2003.2506

*Datum vydání: 26. března 2020*

Tato verze obsahuje následující:

- Nová podpora modifikátorů přístupu v nástroji Q# , další informace najdete v tématu [struktury souborů](xref:microsoft.quantum.guide.filestructure) .
- Aktualizováno na .NET Core SDK 3.1

Podívejte se na úplný seznam uzavřených PR pro [knihovny](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilátor](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [modul runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ukázky](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) a [katy](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01020022610"></a>Verze 0.10.2002.2610

*Datum vydání: 27. února 2020*

Tato verze obsahuje následující:

- Nová knihovna pro kvantové strojové učení. Další informace najdete na naší [dokumentační stránce QML](xref:microsoft.quantum.machine-learning.concepts.intro).
- I Q# opravy chyb, což při načítání balíčků NuGet přináší až 10 20krát zvýšení výkonu

Podívejte se na úplný seznam uzavřených PR pro [knihovny](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilátor](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [modul runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ukázky](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) a [katy](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01020012831"></a>Verze 0.10.2001.2831

*Datum vydání: 29. ledna 2020*

Tato verze obsahuje následující:

- Nový balíček NuGet Microsoft.Quantum.SDK, který nahradí balíček NuGet Microsoft.Quantum.Development.Kit při vytváření nových projektů. Balíček NuGet Microsoft.Quantum.Development.Kit se bude dál podporovat pro už existující projekty. 
- Podpora pro Q# rozšíření kompilátoru, která jsou povolená novým Microsoftem. balíček NuGet NuGet, další informace najdete v [dokumentaci k GitHubu](https://github.com/microsoft/qsharp-compiler/tree/main/src/QuantumSdk#extending-the-q-compiler), [ukázce rozšíření kompilátoru](https://github.com/microsoft/qsharp-compiler/tree/main/examples/CompilerExtensions) a blogu pro [ Q# vývoj](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/) .
- Přidání podpory pro .NET Core 3.1 – důrazně doporučujeme mít nainstalovanou verzi 3.1.100, protože sestavování se staršími verzemi .NET Core SDK může způsobovat problémy
- Nové transformace kompilátoru dostupné v oboru názvů Microsoft.Quantum.QsCompiler.Experimental
- Nová funkce pro vystavení vektorů výstupního stavu jako HTML vQ#
- Přidání podpory pro EstimateFrequencyA do oboru názvů Microsoft.Quantum.Characterization kvůli Hadamardovu a SWAP testu
- AmplitudeAmplification Namespace teď používá Q# vodítko stylu.

Podívejte se na úplný seznam uzavřených PR pro [knihovny](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilátor](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [modul runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ukázky](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) a [katy](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019120501"></a>Verze 0.10.1912.0501

*Datum vydání: 5. prosince 2019*

Tato verze obsahuje následující:

- Nový atribut testu pro Q# testování částí, viz aktualizovaná dokumentace k rozhraní API [tady](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test) a aktualizované testování & Průvodce laděním [tady](xref:microsoft.quantum.guide.testingdebugging)
- Přidání trasování zásobníku v případě Q# chyby běhu programu
- Podpora zarážek v editoru Visual Studio Code vzhledem k aktualizaci [rozšíření OmniSharp C# Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)

Podívejte se na úplný seznam uzavřených PR pro [knihovny](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilátor](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [modul runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ukázky](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) a [katy](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019111607"></a>Verze 0.10.1911.1607

*Datum vydání: 17. listopadu 2019*

Tato verze obsahuje následující:

- Zlepšení výkonu pro [kvantové katy](https://github.com/Microsoft/QuantumKatas) a poznámkové bloky Jupyter

Podívejte se na úplný seznam uzavřených PR pro [knihovny](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilátor](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [modul runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ukázky](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) a [katy](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  


## <a name="version-0101911307"></a>Verze 0.10.1911.307

*Datum vydání: 1. listopadu 2019*

Tato verze obsahuje následující:

- Aktualizace Visual Studio Code & rozšíření sady Visual Studio pro nasazení jazykového serveru jako samostatného spustitelného souboru, který eliminuje závislost verze .NET Core SDK  
- Migrace na .NET Core 3.0
- Změna způsobující chybu pro Microsoft.Quantum.Simulation.Core.IOperationFactory se zavedením nové metody `Fail`. Má vliv jenom na vlastní simulátory, které nerozšiřují SimulatorBase. Další informace [najdete v žádosti o přijetí změn na GitHubu](https://github.com/microsoft/qsharp-runtime/pull/59).
- Nová podpora pro zastaralé atributy

Podívejte se na úplný seznam uzavřených PR pro [knihovny](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilátor](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [modul runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ukázky](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) a [katy](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-0919093002"></a>Verze 0.9.1909.3002

*Datum vydání: 30. září 2019*

Tato verze obsahuje následující:

- Nová podpora pro Q# doplňování kódu v aplikaci Visual Studio 2019 (verze 16,3 & novější) & Visual Studio Code
- Nová [kvantová kata](https://github.com/Microsoft/QuantumKatas) pro kvantové sčítačky

Podívejte se na úplný seznam uzavřených PR pro [knihovny](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilátor](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [modul runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ukázky](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) a [katy](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-09-packagereference-0919082902"></a>Verze 0.9 (*PackageReference 0.9.1908.2902*)

*Datum vydání: 29. srpna 2019*

Tato verze obsahuje následující:

- Nová podpora pro [příkazy conjugation](xref:microsoft.quantum.guide.operationsfunctions#conjugations) v Q#
- Nové akce kódu v kompilátoru, například náhrada, přidání dokumentace a aktualizace položky jednoduchého pole
- Přidané instalační šablony a nové příkazy projektu do rozšíření editoru Visual Studio Code
- Přidané nové varianty kombinátoru ApplyIf, například [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)
- Další [kvantové katy](https://github.com/Microsoft/QuantumKatas) převedené do poznámkových bloků Jupyter
- Rozšíření sady Visual Studio Extension nyní vyžaduje Visual Studio 2019

Podívejte se na úplný seznam uzavřených PR pro [knihovny](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilátor](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [modul runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [ukázky](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) a [katy](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

Změny jsou tady shrnuty včetně pokynů k upgradování vašich existujících programů.  Přečtěte si další informace o těchto změnách na [ Q# blogu pro vývoj](https://devblogs.microsoft.com/qsharp).

## <a name="version-08-packagereference-0819071701"></a>Verze 0.8 (*PackageReference 0.8.1907.1701*)

*Datum vydání: 12. července 2019*

Tato verze obsahuje následující:

- Nová umístění indexů pro řezy polí, další informace najdete v [referenční příručce jazyka](xref:microsoft.quantum.guide.expressions#array-slices).
- Přidání souboru Dockerfile hostovaného na [Container Registry Microsoftu](https://github.com/microsoft/ContainerRegistry), další informace najdete v [ Q# úložišti](https://github.com/microsoft/iqsharp/blob/main/README.md) .
- Zásadní změna [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro), aktualizace nastavení konfigurace, změny názvů; aktualizované názvy najdete v [prohlížeči rozhraní .NET API](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration).

Podívejte se na úplný seznam uzavřených žádostí o přijetí změn (PR) pro [knihovny](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) a [ukázky](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-07-packagereference-0719053109"></a>Verze 0.7 (*PackageReference 0.7.1905.3109*)

*Datum vydání: 31. května 2019*

Tato verze obsahuje následující:
- přidání do Q# jazyka, 
- aktualizace chemické knihovny 
- nová numerická knihovna

Podívejte se na úplný seznam uzavřených žádostí o přijetí změn (PR) pro [knihovny](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) a [ukázky](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Změny jsou tady shrnuty včetně pokynů k upgradování vašich existujících programů.  Přečtěte si další informace o těchto změnách na [ Q# blogu pro vývoj](https://devblogs.microsoft.com/qsharp).

### <a name="no-locq-language-syntax"></a>Q# syntaxe jazyka
Tato verze přidává novou Q# jazykovou syntaxi:
* Byly přidány pojmenované položky pro [uživatelsky definované typy](xref:microsoft.quantum.guide.types#user-defined-types).  
* Konstruktory uživatelsky definovaných typů se teď dají použít jako funkce.
* Byla přidána podpora pro příkazy [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) a [apply-and-reassign](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) v uživatelsky definovaných typech.
* Opravný blok pro smyčky [repeat-until-success](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) je teď volitelný.
* Nyní podporujeme smyčky while ve funkcích (ne v operacích).

### <a name="library"></a>Knihovna 

Tato verze přidává numerickou knihovnu: Přečtěte si další informace o tom, jak [používat novou numerickou knihovnu](xref:microsoft.quantum.numerics.usage) a vyzkoušejte [nové ukázky](https://github.com/microsoft/quantum/tree/main/Numerics).  [PR č. 102](https://github.com/Microsoft/QuantumLibraries/pull/102).  

Tato verze reorganizuje rozšíření a aktualizuje chemickou knihovnu:
* Vylepšuje modularitu komponent, rozšiřitelnost a obecné vyčištění kódu.  [PR č. 58](https://github.com/microsoft/QuantumLibraries/pull/58).
* Přidává podporu pro [multireferenční vlnové funkce](xref:microsoft.quantum.chemistry.concepts.multireference), jak řídké multireferenční vlnové funkce, tak i UCC (unitárně spřažený klastr).  [PR č. 110](https://github.com/Microsoft/QuantumLibraries/pull/110).
* (Děkujeme.) Přispěvatel [1QBit](https://1qbit.com) ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)): Hodnocení energie pomocí variačního přístupu. [PR č. 120](https://github.com/Microsoft/QuantumLibraries/pull/120).
* Aktualizace schématu [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) na novou [verzi 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2) přidáním specifikace unitárně spřaženého klastru. [Problém č. 65](https://github.com/microsoft/QuantumLibraries/issues/65).
* Přidání interoperability Pythonu do funkcí chemické knihovny. Vyzkoušejte si tuto [ukázku](https://github.com/microsoft/Quantum/tree/main/Chemistry/PythonIntegration). [Problém č. 53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR č. 110](https://github.com/Microsoft/QuantumLibraries/pull/110).

## <a name="version-061905"></a>Verze 0.6.1905

*Datum vydání: 3. května 2019*

Tato verze obsahuje následující:
- provede změny v Q# jazyce. 
- restrukturalizace knihoven sady Quantum Development Kit 
- přidání nových ukázek 
- oprava chyb  Několik uzavřených žádostí o přijetí změn (PR) pro [knihovny](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) a [ukázky](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Změny jsou tady shrnuty včetně pokynů k upgradování vašich existujících programů.  Další informace o těchto změnách si můžete přečíst v blogu devblogs.microsoft.com/qsharp.

### <a name="no-locq-language-syntax"></a>Q# syntaxe jazyka
Tato verze přidává novou Q# jazykovou syntaxi:
* Přidán [zkrácený způsob, jak vyjádřit specializace kvantových operací](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations) (řízení a adjungace) pomocí operátorů `+`.  Stará syntaxe je zastaralá.  Programy, které používají starou syntaxi (například `: adjoint`), budou i nadále fungovat, ale vygeneruje se upozornění v době kompilace.  
* Přidán nový operátor pro příkaz [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions), `w/`, který lze použít k rychlému vytvoření pole jako modifikace existujícího pole.
* Přidán běžný [příkaz apply-and-update](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols), například `+=`, `w/=`.
* Přidán způsob, jak zadat krátký název pro obory názvů v [direktivách open](xref:microsoft.quantum.guide.filestructure#open-directives).

V této verzi už nepovolujeme zadat prvek pole na levé straně příkazu set.  Důvodem je, že syntaxe naznačuje, že tato pole jsou měnitelná, a přitom ve skutečnosti výsledkem této operace bylo vždy vytvoření nového pole s modifikací.  Místo toho se vygeneruje chyba kompilátoru s doporučením, aby se ke stejnému výsledku použil nový operátor copy-and-update, `w/`.  

### <a name="library-restructuring"></a>Restrukturalizace knihoven
Tato verze reorganizuje knihovny, aby se umožnil jejich růst konzistentním způsobem:
* Přejmenovává obor názvů Microsoft.Quantum.Primitive na Microsoft.Quantum.Intrinsic.  Tyto operace se implementují cílovým počítačem.  Obor názvů Microsoft.Quantum.Primitive je zastaralý.  Za běhu dojde k upozornění, pokud programy volají operace a funkce pomocí zastaralých názvů.

* Balíček Microsoft.Quantum.Canon se přejmenoval na Microsoft.Quantum.Standard.  Tento balíček obsahuje obory názvů, které jsou společné pro většinu Q# programů.  To zahrnuje:  
    - Microsoft.Quantum.Canon pro běžné operace
    - Microsoft.Quantum.Arithmetic pro aritmetické operace pro obecné účely
    - Microsoft.Quantum.Preparation pro operace používané k přípravě stavu qubitu
    - Microsoft.Quantum.Simulation pro funkce simulace

V důsledku této změny můžou u programů, které obsahují jediný příkaz „open“ pro obor názvů Microsoft.Quatum.Canon, vzniknout chyby sestavení, pokud program odkazuje na operace, které byly přesunuty do ostatních tří nových oborů názvů.  Přidání dalších příkazů otevření pro tři nové obory názvů představuje jednoduchý způsob, jak tento problém vyřešit.  

* Několik oborů názvů je zastaralých, protože obsažené operace byly přeorganizovány do jiných oborů názvů. Programy, které používají tyto obory názvů, budou dál fungovat a varování v době kompilace upozorní na obor názvů, kde je operace definována.  

* Obor názvů Microsoft.Quantum.Arithmetic byl normalizován, aby používal uživatelsky definovaný typ <xref:microsoft.quantum.arithmetic.littleendian>. V případě potřeby převodu na formát Little Endian použijte funkci [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian).  

* Názvy několika volat (funkce a operace) byly změněny tak, aby odpovídaly [ Q# vodítku stylu](xref:microsoft.quantum.contributing.style).  Staré názvy volatelných položek jsou zastaralé.  Programy, které používají staré volatelné položky, budou i nadále fungovat s upozorněním v době kompilace. 

### <a name="new-samples"></a>Nové ukázky

Přidali jsme [ukázku použití Q# s ovladačem F #](https://github.com/Microsoft/Quantum/pull/164).  

**Děkujeme** následujícímu přispěvateli do našeho otevřeného základu kódu na webu http://github.com/Microsoft/Quantum. Tyto příspěvky se významně přidávají do bohatých ukázek Q# kódu:

* Mathias Soeken ([@msoeken](https://github.com/msoeken)): Syntéza funkcí Oracle. [PR č. 135](https://github.com/Microsoft/Quantum/pull/135).

### <a name="migrating-existing-projects-to-061905"></a>Migrace existujících projektů do verze 0.6.1905

Pokyny k aktualizaci sady QDK najdete v [instalační příručce](xref:microsoft.quantum.install).
  
Pokud máte existující Q# projekty ze sady pro vývoj pro všechna množství 0,5, postupujte podle kroků pro migraci těchto projektů na nejnovější verzi.

1. Projekty je potřeba upgradovat postupně.  Pokud máte řešení s více projekty, aktualizujte jednotlivé projekty v pořadí, ve kterém jsou odkazovány.
2. Na příkazovém řádku spusťte příkaz `dotnet clean` a odeberte všechny existující binární soubory a mezilehlé soubory.
3. V textovém editoru upravte soubor .csproj a změňte verzi pro všechny odkazy `PackageReference` balíčků „Microsoft.Quantum“ na verzi 0.6.1904. Název balíčku „Microsoft.Quantum.Canon“ změňte na „Microsoft.Quantum.Standard“. Příklad:

    ```xml
    <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
    <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
    ```
4. Z příkazového řádku spusťte tento příkaz: `dotnet msbuild`  
5. Po jeho spuštění může být pořád potřeba ručně vyřešit chyby kvůli dříve uvedeným změnám.  V mnoha případech budou tyto chyby hlášené funkcí IntelliSense v sadě Visual Studio nebo editoru Visual Studio Code.
    - Otevřete kořenovou složku projektu nebo obsahující řešení v sadě Visual Studio 2019 nebo editoru Visual Studio Code.
    - Po otevření souboru. QS v editoru by se měl zobrazit výstup Q# rozšíření jazyka v okně výstup.
    - Po úspěšném načtení projektu (indikovaném v okně výstupu) otevřete jednotlivé soubory a vyřešte všechny zbývající problémy.

> [!NOTE]
> * Pro verzi 0.6 jazykový server obsažený v sadě Quantum Development Kit nepodporuje víc pracovních prostorů.
> * Pokud chcete pracovat s projektem v editoru Visual Studio Code, otevřete kořenovou složku obsahující vlastní projekt a všechny odkazované projekty.   
> * Pokud chcete pracovat s řešením v sadě Visual Studio, musí být všechny projekty obsažené v řešení ve stejné složce jako řešení nebo v jedné z jejích podsložek.  
> * Odkazy mezi projekty migrovanými do verze 0.6 a vyšší a projekty, které používají starší verze balíčků, **nejsou** podporované.

## <a name="version-051904"></a>Verze 0.5.1904

*Datum vydání: 15. dubna 2019*

Tato verze obsahuje opravy chyb.


## <a name="version-051903"></a>Verze 0.5.1903

*Datum vydání: 27. března 2019*

Tato verze obsahuje následující:

- Přidává podporu pro Jupyter Notebook, která nabízí skvělý způsob, jak se dozvědět víc Q# .  [Podívejte se na nové ukázky Jupyter Notebook a naučte se psát vlastní poznámkové bloky](xref:microsoft.quantum.install). 

- Přidává do knihovny Quantum Canon aritmetiku celočíselné sčítačky.  Projděte si také Jupyter Notebook, který [popisuje způsob použití nových celočíselných sčítaček](https://github.com/microsoft/Quantum/blob/main/samples/arithmetic/AdderExample.ipynb).

- Oprava chyby pro problém DumpRegister hlášených komunitou ([č. 148](https://github.com/Microsoft/Quantum/issues/148)).

- Přidání možnosti vrácení z [příkazu using](xref:microsoft.quantum.guide.qubits#allocating-qubits).

- Přepracování [úvodní příručky](xref:microsoft.quantum.install).


## <a name="version-051902"></a>Verze 0.5.1902

*Datum vydání: 27. února 2019*

Tato verze obsahuje následující:

- Přidává podporu pro hostitele Pythonu pro různé platformy.  `qsharp`Balíček pro Python usnadňuje simulaci Q# operací a funkcí v rámci Pythonu. Přečtěte si další informace o [interoperabilitě Pythonu](xref:microsoft.quantum.install). 

- Rozšíření sady Visual Studio a editoru Visual Studio Code nyní podporují přejmenování symbolů (například funkcí a operací).

- Rozšíření sady Visual Studio se teď dá nainstalovat do sady Visual Studio 2019.

## <a name="version-041901"></a>Verze 0.4.1901

*Datum vydání: 30. ledna 2019*

Tato verze obsahuje následující:

- Přidává podporu pro nový primitivní typ, BigInt, který představuje celé číslo se znaménkem libovolné velikosti.  Přečtěte si další informace o [typu BigInt](xref:microsoft.quantum.guide.types).
- Přidává nový simulátor Toffoli, rychlý simulátor pro zvláštní účely, který může simulovat kvantové operace X, CNOT a vícenásobně řízené operace X s velkým počtem qubitů.  Přečtěte si další informace o [simulátoru Toffoli](xref:microsoft.quantum.machines.toffoli-simulator).
- Přidá jednoduchý Estimator prostředků, který odhadne prostředky potřebné ke spuštění dané instance Q# operace v počítači s více operačními systémy.  Přečtěte si další informace o [estimátoru prostředků](xref:microsoft.quantum.machines.resources-estimator).


## <a name="version-0318112802"></a>Verze 0.3.1811.2802

*Datum vydání: 28. listopadu 2018*

I když naše rozšíření VS Code ho nepoužívalo, bylo označeno a odebráno z webu Marketplace během [čištění rozšíření](https://code.visualstudio.com/blogs/2018/11/26/event-stream) souvisejícího s balíčkem NPM `event-stream`. Tato verze odebírá všechny běhové závislosti, které by mohly způsobit, že rozšíření aktivuje nějakou výstrahu.

Pokud jste dříve rozšíření nainstalovali, budete ho muset nainstalovat znovu, a to tak, že na webu Visual Studio Marketplace najdete rozšíření [Microsoft Quantum Development Kit for Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode) a stisknete Instalovat. Omlouváme se za nepříjemnosti.


## <a name="version-0318111511"></a>Verze 0.3.1811.1511

*Datum vydání: 20. listopadu 2018*

Tato verze opravuje chybu, která bránila některým uživatelům v úspěšném načtení rozšíření sady Visual Studio.

## <a name="version-031811203"></a>Verze 0.3.1811.203

*Datum vydání: 2. listopadu 2018*

Tato verze zahrnuje několik oprav chyb, včetně:

* Vyvolání `DumpMachine` může v určitých situacích změnit stav simulátoru.
* Odebrání upozornění kompilace při sestavování projektů pomocí verze .NET Core dřívější než 2.1.403.
* Vyčištění dokumentace, speciálně popisů zobrazovaných při najetí myší v editoru VS Code nebo sadě Visual Studio.

## <a name="version-0318102508"></a>Verze 0.3.1810.2508

*Datum vydání: 29. října 2018*

Tato verze zahrnuje nové funkce jazyka a vylepšené vývojové prostředí:

* Tato verze zahrnuje jazykový Server pro i Q# integraci klientů pro Visual Studio a Visual Studio Code. To umožňuje novou sadu funkcí IntelliSense spolu s živou odezvou během psaní ve formě podtržení chyb a upozornění. 
* Tato aktualizace významně vylepšuje diagnostické zprávy, a to díky snadné navigaci a přesným rozsahům pro diagnostiku a dalším podrobnostem v informacích zobrazených při najetí myší.
* Q#Jazyk se rozšířil způsobem, který sjednocuje způsob, jakým vývojáři můžou provádět běžné operace, a nové vylepšení jazykových funkcí pro výkonné okamžité výpočty.  V této verzi jsme několik zásadní změny Q# jazyka.   

Tato verze taky obsahuje novou kvantovou chemickou knihovnu.

* Chemická knihovna obsahuje nové funkce hamiltoniánských simulací, mimo jiné tyto:
    - Trotter-Suzukiho integrátory libovolného sudého řádu pro lepší přesnost simulace.
    - Simulační technika qubitizace s optimalizací zaměřenou na chemii ke snížení složitosti hradla $T$.
* Nové opensourcové schéma, nazývané Broombridge (v odkazu na [most](https://en.wikipedia.org/wiki/Broom_Bridge) oslavovaný jako místo narození hamiltoniánů), je zavedené pro import reprezentací molekul a jejich simulace.
* K dispozici je více chemických reprezentací definovaných pomocí schématu Broombridge.  Tyto modely byly vygenerovány pomocí [NWChem](http://www.nwchem-sw.org/), což je opensourcový chemický nástroj pro vysoce výkonné výpočty.
* Kurzy a ukázky popisují, jak použít chemickou knihovnu a datové modely Broombridge k těmto akcím:
    - Konstrukce jednoduchých hamiltoniánů pomocí chemické knihovny
    - Vizualizace energií základního a excitovaného stavu hydridu lithného pomocí odhadu fáze.
    - Provádění odhadů prostředků pro kvantovou chemickou simulaci.
    - Odhad energetických úrovní molekul reprezentovaných schématem Broombridge.
* Dokumentace popisuje, jak používat NWChem k vygenerování dalších chemických modelů pro simulaci provozu Q# .

Přečtěte si další informace o [chemické knihovně sady Quantum Development Kit](xref:microsoft.quantum.chemistry.concepts.intro).

S novou chemickou knihovnou oddělíme knihovny do nového úložiště GitHub [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries).  Ukázky zůstanou v úložišti [Microsoft/Quantum](https://github.com/Microsoft/Quantum).  Uvítáme příspěvky do obou!

Tato verze zahrnuje opravy chyb a funkce pro problémy hlášené komunitou:

* IntelliSense pro Q# ? ([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).
* Soubory .qs ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).
* Vylepšení chybové zprávy při zkrácení složených závorek v příkazu if ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).
* Podpora dekonstrukce řazené kolekce členů při proměnlivé (opakované) vazbě ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).
* Chyba při spuštění poskytnutého kódu BitFlipCode ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).
* H2SimulationGUI někdy zobrazuje velké špičky ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).

### <a name="community-contributions"></a>Komunitní příspěvky

**Děkujeme** následujícím přispěvatelům do našeho otevřeného základu kódu na webu http://github.com/Microsoft/Quantum. Tyto příspěvky se významně přidávají do bohatých ukázek Q# kódu:

* Rolf Huisman ( [@RolfHuisman](https://github.com/RolfHuisman) ): vylepšené prostředí pro QASM/ Q# vývojáře vytvořením QASM pro Q# překladatele. [PR č. 58](https://github.com/Microsoft/Quantum/pull/58).

* Andrew Helwer ([@ahelwer](https://github.com/ahelwer)):  Příspěvek ukázky implementace hry CHSH, kvantové hry související s nelokalitou.  [PR č. 84](https://github.com/Microsoft/Quantum/pull/84).

Děkujeme také uživatelům Rohit Gupta ([@guptarohit](https://github.com/guptarohit),[PR č. 90](https://github.com/Microsoft/quantum/pull/90)), Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[PR č. 289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)) a Lee James O'Riordan ([@mlxd](https://github.com/mlxd),[PR č. 96](https://github.com/Microsoft/Quantum/pull/96)) za jejich práci na vylepšení obsahu dokumentace pro nás všechny a za odstranění chyb a překlepů! 

## <a name="version-021809701"></a>Verze 0.2.1809.701

*Datum vydání: 10. září 2018*

Tato verze zahrnuje opravy chyb pro problémy hlášené komunitou. Mezi ně patří:

* Nelze použít operátor shift ([GitHub](https://github.com/Microsoft/Quantum/issues/75)).
* Při tisku na konzole selže `DumpMachine` / `DumpRegister` pro `QCTraceSimulator` ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680)).
* Je možné přidělit 0 qubitů ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits)).
* `AssertQubitState` vyžaduje explicitní volání Complex() ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call)).
* Operace `Measure` vždycky vrací `One` v systému macOS ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).

Děkujeme! 

## <a name="version-0218063001"></a>Verze 0.2.1806.3001

*Datum vydání: 30. června 2018*

Tato vydání je jenom Rychlá oprava pro [problém #48 nahlášená na GitHubu](https://github.com/Microsoft/Quantum/issues/48) ( Q# Pokud uživatelské jméno obsahuje prázdné místo), kompilace se nezdařila. Použijte stejné pokyny k aktualizaci jako pro `0.2.1806.1503` s odpovídající novou verzí (`0.2.1806.3001-preview`).

## <a name="version-0218061503"></a>Verze 0.2.1806.1503

*Datum vydání: 22. června 2018*

Tato verze zahrnuje několik příspěvků komunity a také vylepšené prostředí pro ladění a lepší výkon.  Konkrétně:

* Zvýšení výkonu u malých i velkých simulací pro cílový počítač QuantumSimulator.
* Vylepšené funkce ladění.
* Komunitní příspěvky v opravách chyb, nové funkce pomocníka, operace a nové ukázky.

### <a name="performance-improvements"></a>Zlepšení výkonu

Tato aktualizace zahrnuje významná vylepšení výkonu pro simulaci velkých a malých počtů qubitů pro všechny cílové počítače.  Toto zlepšení je snadno vidět u simulace H<sub>2</sub>, která je standardní ukázkou v sadě Quantum Development Kit.

### <a name="improved-debugging-functionality"></a>Vylepšené funkce ladění

Tato aktualizace přidává nové funkce ladění:
* Byly přidány dvě nové operace, @"microsoft.quantum.extensions.diagnostics.dumpmachine" a @"microsoft.quantum.extensions.diagnostics.dumpregister", jejichž výstupem jsou informace vlnové funkce o cílovém kvantovém počítači v časovém bodě.  
* V sadě Visual Studio se teď pravděpodobnost měření $\ket{1}$ na jednotlivém qubitu automaticky zobrazí v okně ladění pro cílový počítač QuantumSimulator.
* V sadě Visual Studio se zlepšilo zobrazení vlastností proměnných v oknech ladění **Autos** a **Locals**. 

Přečtěte si další informace o [testování a ladění](xref:microsoft.quantum.guide.testingdebugging).

### <a name="community-contributions"></a>Komunitní příspěvky

Q#Komunita programátor roste a jsme nadšená Zi, aby viděli prvního uživatele, který přispěl ke knihovně a ukázkám, které byly odeslány na náš základ pro otevření kódu na adrese http://github.com/Microsoft/quantum .  **Opravdu děkujeme** následujícím přispěvatelům:
* Mathias Soeken ([@msoeken](https://github.com/msoeken)): přispěl ukázkou definující metodu logické syntézy na základě transformace, která konstruuje Toffoliho sítě pro implementaci dané permutace. Kód se zapisuje výhradně v rámci Q# funkcí a operací.  [PR č. 41](https://github.com/Microsoft/Quantum/pull/41).
* RolfHuisman ( [@RolfHuisman](https://github.com/RolfHuisman) ): Microsoft MVP Rolf Huisman navrhl ukázku, která generuje nestrukturovaný QASM kód z Q# kódu pro omezenou třídu programů, které nemají tok klasického řízení a omezené operace. [PR č. 59](https://github.com/Microsoft/Quantum/pull/59)
* Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)): pomohla zlepšit náš základ kódu odesláním knihovní funkce pro řízené operace. [PR č. 53](https://github.com/Microsoft/Quantum/pull/53)
* Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)): opravila @"microsoft.quantum.canon.quantumphaseestimation" a vytvořila nové testy jednotek.  [PR č. 54](https://github.com/Microsoft/Quantum/pull/54)
* Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)): vyčistil ukázku teleportace zajištěním, že se instance QuantumSimulator odstraní. [PR č. 20](https://github.com/Microsoft/Quantum/pull/20)

Navíc **velké poděkování** od přispěvatelů týmu Commercial Engineering Services těm softwarovým inženýrům Microsoftu, kteří během hackathonu provedli cenné změny v naší dokumentaci.  Jejich změny výrazně vylepšily přehlednost a onboarding pro všechny z nás:
* Sascha Corti
* Mihaela Curmei
* John Donnelly
* Kirill Logachev
* Jan Pospisil
* Anita Ramanan
* Frances Tibble
* Alessandro Vozza

### <a name="update-existing-projects"></a>Aktualizace stávajících projektů

Tato verze je plně zpětně kompatibilní. Stačí aktualizovat balíčky NuGet v projektech na verzi `0.2.1806.1503-preview` a provést **úplné opětovné sestavení**, aby se zajistilo nové vygenerování všech přechodných soubory.

V aplikaci Visual Studio postupujte podle obvyklých pokynů jak [aktualizovat balíček](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package).

Chcete-li aktualizovat šablony projektů pro příkazový řádek, spusťte následující příkaz:
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

Po spuštění tohoto příkazu všechny nové projekty vytvořené pomocí příkazu `dotnet new <project-type> -lang Q#` automaticky použijí tuto verzi sady Quantum Development Kit.

Chcete-li aktualizovat existující projekt, aby používal nejnovější verze, spusťte následující příkaz v adresáři pro každý projekt:

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

Pokud existující projekt také používá integraci XUnit pro testování částí, pak je možné použít podobný příkaz i k aktualizaci balíčku:
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

V závislosti na verzi XUnit, kterou testovací projekt používá, může být také nutné aktualizovat XUnit na verzi 2.3.1:
```
dotnet add package xunit -v "2.3.1" 
```

Po aktualizaci se ujistěte, že jste odebrali všechny dočasné soubory vygenerované předchozí verzí, a to takto:
```
dotnet clean 
```

### <a name="known-issues"></a>Známé problémy

Nejsou žádné další známé problémy, které by bylo možné ohlásit.


## <a name="version-0218022202"></a>Verze 0.2.1802.2202

*Datum vydání: 26. února 2018*

Tato verze přináší podporu pro vývoj na více platformách, interoperabilitu jazyků a vylepšení výkonu. Konkrétně:

- Podpora pro vývoj na bázi systémů macOS a Linux. 
- Kompatibilita .NET Core, včetně podpory pro Visual Studio Code napříč platformami.
- Úplná opensourcová licence pro knihovny sady Quantum Development Kit.
- Vylepšený výkon simulátoru v projektech vyžadujících 20 nebo více qubitů.
- Interoperabilita s jazykem Python (verze Preview dostupná ve Windows).

### <a name="net-editions"></a>Edice .NET

Platforma .NET je dostupná prostřednictvím dvou různých edic, .NET Framework, která je součástí Windows, a opensourcové .NET Core, která je k dispozici pro Windows, macOS a Linux.
V této verzi je většina částí sady Quantum Development Kit poskytována jako knihovny pro .NET Standard, sadu tříd společných pro Framework i Core.
Tyto knihovny jsou proto kompatibilní s nejnovějšími verzemi .NET Framework i .NET Core.

Aby se zajistila co největší přenositelnost projektů napsaných pomocí sady Quantum Development Kit, doporučujeme, aby projekty knihoven napsané pomocí sady Quantum Development Kit cílily na .NET Standard, zatímco konzolové aplikace cílily na .NET Core.
Vzhledem k tomu, že předchozí verze sady Quantum Development Kit podporovaly jenom .NET Framework, možná budete muset migrovat stávající projekty. Podrobnosti o tom, jak to udělat, najdete dál.

### <a name="project-migration"></a>Migrace projektu

Projekty vytvořené pomocí předchozích verzí sady Quantum Development Kit budou pořád fungovat, dokud neaktualizujete balíčky NuGet, které jste v nich použili. Chcete-li migrovat existující kód na novou verzi, proveďte následující kroky:
1. Vytvořte nový projekt .NET Core pomocí správného typu Q# šablony projektu (aplikace, knihovna nebo projekt testů).
2. Zkopírujte existující soubory .qs a .cs/.fs z původního projektu do nového projektu (pomocí Přidat > Existující položka). Nekopírujte soubor AssemblyInfo.cs.
3. Sestavte a spusťte nový projekt.

Počítejte s tím, že operace RandomWalkPhaseEstimation z oboru názvů Microsoft.Quantum.Canon byla přesunuta do oboru názvů Microsoft.Research.Quantum.RandomWalkPhaseEstimation v úložišti [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc).

### <a name="known-issues"></a>Známé problémy

- `--filter`Možnost `dotnet test` nefunguje správně u testů napsaných v Q# .
  V důsledku toho nelze jednotlivé testy jednotek spustit v Visual Studio Code; `dotnet test` k opětovnému spuštění všech testů doporučujeme použít na příkazovém řádku.

## <a name="version-0118011707"></a>Verze 0.1.1801.1707

*Datum vydání: 18. ledna 2018*

Tato verze opravuje některé problémy hlášené komunitou. Konkrétně:

- Simulátor teď funguje s dřívějšími procesory bez podpory AVX.
- Místní nastavení typu Decimal nebude způsobit Q# selhání analyzátoru.
- Primitivní operace `SignD` nyní vrací typ `Int`, a ne `Double`.


## <a name="version-011712901"></a>Verze 0.1.1712.901

*Datum vydání: 11. prosince 2017*

### <a name="known-issues"></a>Známé problémy

#### <a name="hardware-and-software-requirements"></a>Požadavky na hardware a software

- Simulátor, který je součástí sady Quantum Development Kit, vyžaduje ke spuštění 64bitovou instalaci Microsoft Windows.
- Kvantový simulátor Microsoftu, který se instaluje se sadou Quantum Development Kit, využívá rozšíření AVX (Advanced Vector Extension) a vyžaduje procesor s podporou AVX. Procesory Intel dodávané v 1. čtvrtletí 2011 (Sandy Bridge) nebo novější podporují AVX. Vyhodnocujeme podporu starších procesorů a můžeme později oznámit podrobnosti.

#### <a name="project-creation"></a>Vytvoření projektu

- Při vytváření řešení (. sln), které bude používat Q# , musí být řešením jeden adresář vyšší než každý projekt (. csproj) v řešení. Při vytváření nového řešení to můžete udělat tak, že v dialogovém okně Nový projekt zaškrtnete políčko Vytvořit adresář pro řešení. Pokud to neuděláte, balíčky NuGet sady Quantum Development Kit budou muset být nainstalovány ručně.

#### Q#

- Technologie IntelliSense nezobrazí správné chyby pro Q# kód. Ujistěte se, že se zobrazují chyby sestavení v aplikaci Visual Studio Seznam chyb, aby se zobrazily správné Q# chyby. Všimněte si také, že Q# chyby nebudou zobrazeny až po dokončení sestavení.
- Použití měnitelného pole v částečné aplikaci může vést k neočekávanému chování.
- Vazba neměnného pole s měnitelným polem (let a = b, kde b je měnitelné pole) může vést k neočekávanému chování.
- Profilace, pokrytí kódu a jiné moduly plug-in VS nemůžou vždycky počítat Q# řádky a bloky přesně.
- Q#Kompilátor neověřuje interpolované řetězce. Je možné vytvořit chyby kompilace C# pomocí názvů proměnných s chybou pravopisu nebo pomocí výrazů v Q# interpolovaná řetězce.

#### <a name="simulation"></a>Simulace

- Kvantový simulátor používá OpenMP k paralelizaci potřebné lineární algebry. Ve výchozím nastavení používá OpenMP všechna dostupná hardwarová vlákna, což znamená, že programy s malým počtem qubitů budou často běžet pomalu, protože požadovaná koordinace bude převyšovat skutečnou práci. To se dá napravit nastavením proměnné prostředí OMP_NUM_THREADS na malé číslo. Hrubým odhadem je 1 vlákno vhodné až do přibližně 4 qubitů, a pak je dobré další vlákno na každý qubit, i když to velmi závisí na vašem algoritmu.

#### <a name="debugging"></a>Ladění

- F11 (krok in) nefunguje v Q# kódu.
- Zvýrazňování kódu v Q# kódu na zarážce nebo pozastavení v jednom kroku je někdy nepřesné. Bude zvýrazněn správný řádek, ale v některých případech bude zvýraznění na řádku začínat a končit v nesprávném sloupci.

#### <a name="testing"></a>Testování

- Testy musí být spuštěny v režimu 64. Pokud testy selžou s výjimkou BadImageFormatException, přejděte do nabídky Test a vyberte Nastavení testu > Výchozí architektura procesoru > x64.
- Některým testům trvá spuštění dlouhou dobu (až 5 minut v závislosti na vašem počítači). To je normální, protože některé využívají víc než dvacet qubitů. Náš největší test aktuálně běží na 23 qubitech.

#### <a name="samples"></a>ukázky

- Na některých počítačích můžou některé malé ukázky běžet pomalu, pokud není proměnná prostředí OMP_NUM_THREADS nastavená na 1. Viz také poznámka k verzi v části Simulace.

#### <a name="libraries"></a>Knihovny

- Implicitně se předpokládá, že qubity předané do operace v různých argumentech jsou všechny jedinečné. Například všechny operace knihovny (a všechny simulátory) předpokládají, že dva qubity předané do kontrolované operace NOT jsou různé qubity. Porušení tohoto předpokladu může vést nepředvídatelným následkům. Tuto podmínku můžete otestovat pomocí simulátoru trasování kvantového počítače.
- Funkce Microsoft.Quantum.Bind nemusí ve všech případech fungovat podle očekávání.
- V oboru názvů Microsoft.Quantum.Extensions.Math vrátí funkce SignD hodnotu Double, nikoli Int, i když základní funkce System.Math.Sign vždy vrátí celé číslo. Je bezpečné porovnat výsledek s hodnotami 1,0, -1,0 a 0,0, protože tyto hodnoty Double mají exaktní binární reprezentace.
