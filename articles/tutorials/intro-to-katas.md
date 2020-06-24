---
title: Seznámení s kvantovými katami
description: Další informace o katách (tréninkových cvičeních) poskytovaných se sadou Microsoft Quantum Development Kit (QDK)
author: bradben
ms.author: bradben
ms.date: 06/02/2020
ms.topic: overview
uid: microsoft.quantum.overview.katas
ms.openlocfilehash: 1c4dfa5c47aa38935cd5936cd256e357b6605371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274722"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>Učte se provádět kvantové výpočty s kvantovými katami

Procesory [katas](https://github.com/Microsoft/QuantumKatas/) představují Open Source kurzy s vlastním tempem a programovací cvičení zaměřené na výuku prvků pro práci s procesory a příznakem Q # ve stejnou dobu.

## <a name="learning-by-doing"></a>Praktická výuka

Kurzy a cvičení shromážděné v tomto projektu jsou zaměřené na praktickou výuku: nabízí programovací úkoly, které pokrývají určitá témata, od velmi jednoduchých k docela náročným. Každý úkol vyžaduje zadání nějakého kódu. První úkoly můžou vyžadovat třeba jenom jeden řádek a poslední už poměrně značný fragment kódu.

Nejdůležitější je, že katas zahrnuje testovací architektury, které se nastavují, spouštějí a ověřují řešení pro úlohy. To vám dá okamžitou zpětnou vazbu k vašemu řešení a umožní znovu si promyslet přístup, pokud není správný.

Katas můžete použít ke studiu ve vašem prostředí dle vašeho výběru:

* Online poznámkové bloky Jupyter v rámci prostředí Binder
* Poznámkové bloky Jupyter spuštěné ve vašem místním počítači
* Visual Studio
* Visual Studio Code

## <a name="what-can-i-learn-with-the-quantum-katas"></a>Jak se můžu učit s využitím kvantových kat?

Seznamte se se základními a základními informacemi o výpočetním prostředí nebo podrobně, které jsou hlubší až do algoritmů a protokolů. Doporučujeme vám na začátku postupovat podle tohoto studijního programu, abyste si bezpečně osvojili základní koncepce kvantových výpočtů. Samozřejmě můžete přeskočit témata, která ovládáte, jako je komplexní aritmetika, a učit se algoritmy v libovolném pořadí.

### <a name="introduction-to-quantum-computing-concepts"></a>Úvod do koncepcí kvantových výpočtů

| Kata | Description |
|:-----|-------------|
|[Komplexní aritmetika](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)|V tomto kurzu se dozvíte o některých matematických pozadích potřebných pro práci s výpočetním prostředím, jako je například imaginární a komplexní číslo.|
|[Lineární algebra](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)|Lineární algebraický se používá k reprezentování stavových a provozních operací ve výpočetním prostředí. Tento kurz se zabývá základy, včetně matric a vektorů.|
|[Koncepce qubitu](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/Qubit)|Seznamte se s qubits – jednou ze základních konceptů náročné na výpočetní výkon. |
|[Jednoqubitová kvantová hradla](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates)|V tomto kurzu se seznámíte s qubitmi nehlášenými procesory, které fungují jako stavební kameny algoritmů pro plnění a transformují qubit stavy v různých způsobech.|
|[Vícequbitové systémy](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitSystems)|Tento kurz zavádí qubit systémy, jejich reprezentace v matematickém zápisu a v kódu Q # a koncept entanglement.|
|[Qubitch procesorů pro více procesorů](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitGates)|Tento kurz se řídí kurzem qubit pro každý [procesor](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates) a zaměřuje se na použití bran na více procesorech k qubit systémům.|

### <a name="quantum-computing-fundamentals"></a>Základní kvantových výpočtů

| Kata | Description |
|:-----|-------------|
|[Rozlišování kvantových hradel](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)|Série cvičení navržených tak, aby se seznámili se základními branami pro plnění v Q #. Zahrnuje cvičení pro základní qubit a multi-qubit brány, sousední a řízené brány a použití bran pro úpravu stavu qubit.|
|[Vytváření kvantové superpozice](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)|Pomocí těchto cvičení seznámení s konceptem základní pozice a programování v Q #. Zahrnuje cvičení pro základní qubit a multi-qubit brány, nadpozice a řízení toku a rekurze v Q #.|
|[Rozlišování kvantových stavů pomocí měření](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)|Tyto cvičení vyřešte při učení o měřeních a kolmých a nekolmých státech. |
|[Spojená měření](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)|Přečtěte si o společných měřeních parity a o tom, jak použít operaci [měření](xref:microsoft.quantum.intrinsic.measure) k odlišení stavových stavů.|

### <a name="algorithms"></a>Algoritmy

| Kata | Description |
|:-----|-------------|
|[Kvantová teleportace](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)|V tomto Kata se prozkoumá navýšení stavových procesorů – protokol, který umožňuje komunikaci se stavem po jednotlivých klasických komunikacích a dříve sdílených entanglement.|
|[Superhusté kódování](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)|Zhuštěné kódování je protokol, který umožňuje přenos dvou bitů klasických informací tím, že posílá jenom jeden qubit s využitím dříve sdílených entanglement.  |
|[Deutsch-Jozsův algoritmus](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringDeutschJozsaAlgorithm)|Tento algoritmus je slavných pro jeden z prvních příkladů algoritmu, který je exponenciálně rychlejší než jakýkoli deterministický klasický algoritmus.|
|[Zkoumání vlastností Groverova vyhledávacího algoritmu na vysoké úrovni](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringGroversAlgorithm)|Základní Úvod k jednomu z nejúčinnějších slavných algoritmů při práci s procesorem. Řeší problém hledání vstupu do černého pole (Oracle), které vytváří určitý výstup. |
|[Implementace Groverova vyhledávacího algoritmu](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)|Tento Kata komentáře je hlubší do vyhledávacího algoritmu Grover a zabývá se psaním Oracle, prováděním kroků algoritmu a nakonec bez něj.|
|[Řešení reálných problémů pomocí algoritmu Grover: problémy s SAT](https://github.com/microsoft/QuantumKatas/tree/master/SolveSATWithGrover)|Řada cvičení, která používá algoritmus Grover k řešení reálných problémů, pomocí [logických problémů s požadavky](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem) (SAT) jako příklad.  |
|[Řešení reálných problémů pomocí algoritmu Grover: Graph – barevné problémy](https://github.com/microsoft/QuantumKatas/tree/master/GraphColoring)| Tento Kata dále zkoumá algoritmus Grover, tentokrát k řešení [problémů spokojenosti s omezeními](https://en.wikipedia.org/wiki/Constraint_satisfaction_problem), a to pomocí grafu, který v příkladu vybarví problém. |

### <a name="protocols-and-libraries"></a>Protokoly a knihovny

| Kata | Description |
|:-----|-------------|
|[Protokol BB84 pro distribuci kvantových klíčů](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)|Přečtěte si o a implementujte protokol distribuce klíčů pro [BB84](https://en.wikipedia.org/wiki/BB84), který používá qubits k výměně kryptografických klíčů. |
|[Bit-překlopit chybovou korekci kódu](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)|Prozkoumejte opravy chyb na základě stavových procesorů nejjednodušším z kódů pro opravu chyb s příznakem chyby (QEC) – tři qubit kód pro překlopení.|
|[Odhad fáze](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)|Algoritmy odhadu fáze jsou některé z nejdůležitějších stavebních bloků pro výpočetní výkon. Přečtěte si o odhadu fáze pomocí těchto cvičení, která zahrnují odhad fáze a postup přípravy a spuštění rutin odhadu fáze v Q #.|
|[Aritmetické operace: sestavování Ripple – přenosná přidání](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)|Podrobná řada cvičení, která prochází [Ripple](https://en.wikipedia.org/wiki/Adder_(electronics)#Ripple-carry_adder) , se doplňují do počítače s procesorem. Sestavte přihlašování na místě, rozbalte ho s jiným algoritmem a nakonec vytvořte místní tahač za běhu na místě.   |

### <a name="entanglement-games"></a>Hry s provázáním

| Kata | Description |
|:-----|-------------|
|[Hra CHSH](https://github.com/microsoft/QuantumKatas/tree/master/CHSHGame)|Prozkoumejte plnění entanglement s implementací hry [CHSH](https://en.wikipedia.org/wiki/CHSH_inequality) . Tato [nemístní](https://en.wikipedia.org/wiki/Quantum_refereed_game) hra ukazuje, jak se dá entanglement používat ke zvýšení pravděpodobnosti výhry hráčů nad rámec toho, co by bylo možné s čistě klasickými strategiemi.|
|[Hra GHZ](https://github.com/microsoft/QuantumKatas/tree/master/GHZGame)|Hra GHZ je jinou nemístní hrou, ale zahrnuje tři hráče.|
|[Mermin-Peresův magický čtverec](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)|Série cvičení, které prozkoumají [pseudo-The-path](https://en.wikipedia.org/wiki/Quantum_pseudo-telepathy#The_Mermin%E2%80%93Peres_magic_square_game) , aby se vyřešila Magic čtvercová hra.  |

## <a name="resources"></a>Zdroje a prostředky

Kompletní řada [kvantových kat](https://github.com/microsoft/QuantumKatas)

[Spustit katy online](https://aka.ms/try-quantum-katas)
