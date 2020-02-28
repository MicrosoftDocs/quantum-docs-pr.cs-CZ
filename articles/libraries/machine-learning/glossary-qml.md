---
title: Knihovna strojového učení
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 2/27/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.training
ms.openlocfilehash: f9b33a607a892179795d0700ba3080f9a24ab94a
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909768"
---
# <a name="quantum-machine-learning-glossary"></a>Machine Learning Glosář

Školení klasifikátoru, zaměřené na okruhy, je proces s mnoha pohybujícími se částmi, které vyžadují stejné (nebo mírně větší) množství kalibrace v rámci zkušební verze a chyby jako školení tradičních klasifikátorů. Tady definujeme hlavní koncepty a složky tohoto školicího procesu.

## <a name="trainingtesting-schedules"></a>Plány školení a testování

V kontextu školení třídění *plán* popisuje podmnožinu ukázek dat v celkovém školení nebo testovací sadě. Plán je obvykle definován jako kolekce ukázkových indexů.

## <a name="parameterbias-scores"></a>Skóre parametru nebo posunu

Vzhledem ke vektoru parametru kandidáta a posunu klasifikátoru se jejich *skóre ověření* měří vzhledem k zvolenému plánu ověřování S a je vyjádřeno počtem chybných klasifikací zjištěných ve všech ukázkách v plánu S.

## <a name="hyperparameters"></a>Hyperparameters

Proces školení modelů se řídí některými předem nastavenými hodnotami nazvanými *parametry*:

### <a name="learning-rate"></a>Studijní frekvence

Jedná se o jeden z klíčových parametrů. Definuje, kolik aktuálního odhadu stochastického přechodu ovlivňuje aktualizaci parametru. Velikost rozdílových hodnot aktualizace parametru je úměrná míře učení. Menší hodnoty studijních kurzů vedou k pomalejšímu vývoji parametrů a pomalejším krokům, ale příliš velké hodnoty LR můžou sbližování zcela rozdělit, protože klesání na určitý místní minimum se nepotvrdí. I když je rychlost učení adaptivní úpravou sledovacího algoritmu v určitém rozsahu, je důležité vybrat vhodnou počáteční hodnotu. Obvyklá výchozí počáteční hodnota pro studijní frekvenci je 0,1. Výběr nejlepší hodnoty studijní frekvence je jemný obrázek (například oddíl 4,3 z Goodfellow et al., "obsáhlý Learning", MIT Press, 2017).

### <a name="minibatch-size"></a>Velikost Minibatch

Definuje, kolik ukázek dat se používá pro jeden odhad stochastického přechodu. Větší hodnoty minibatch velikosti obvykle vedou k větší robustnosti a většímu monotónní konvergenci, ale mohou potenciálně zpomalit proces školení, protože náklady na jeden odhad přechodu jsou úměrné velikosti minimatch. Obvyklá výchozí hodnota pro velikost minibatch je 10.

### <a name="training-epochs-tolerance-gridlocks"></a>Školení epochs, tolerance, gridlocks

"Epocha" znamená jedno úplné předání prostřednictvím naplánovaných školicích dat.
Maximální počet epochs na školicí vlákno (viz níže) by měl být omezené. Školicí vlákno je definováno k ukončení (s nejlépe známými parametry kandidáta), pokud byl spuštěn maximální počet epochs. Nicméně takové školení bude ukončeno dříve, pokud nechybná míra klasifikace u plánu ověření klesne pod zvolenou toleranci. Předpokládejme například, že chybná tolerance klasifikace je 0,01 (1%); Pokud se v sadě ověření 2000 ukázek zobrazuje méně než 20 chybných klasifikací, pak byla dosažena úroveň tolerance. Školicí vlákno se také předčasně ukončí, pokud skóre ověření modelu kandidáta neukazuje žádné vylepšení více po sobě jdoucích epochs (Gridlock). Logika pro ukončení Gridlock je aktuálně pevně zakódované.

### <a name="measurements-count"></a>Počet měření

Odhad skóre pro školení a ověření a součásti stochastického přechodu na zařízení na základě počtu stavů se překrývají, což vyžaduje více měření odpovídajících observables. Počet měření se má škálovat jako $O (1/\ Epsilon ^ 2) $ kde $ \epsilon $ je požadovaná chyba odhadu.
Jako pravidlo pro palec může být počáteční počet měření přibližně $1/\ mbox {tolerance} ^ 2 $ (viz definice tolerance v předchozím odstavci). V takovém případě je potřeba zkontrolovat počet měření vzhůru, pokud se překlesání přechodu jeví jako příliš nestabilní a konvergence není příliš těžká k dosažení.

### <a name="training-threads"></a>Školicí vlákna

Pravděpodobnost, která je přístupným nástrojem pro třídění, je velmi zřídka konvexní, což znamená, že má obvykle velké množství místních Optima v prostoru parametru, který může být významně odlišný od kvality. Vzhledem k tomu, že se proces SGD dá konvergovat pouze k jednomu konkrétnímu optimálnímu, je důležité prozkoumat více počátečních vektorů parametrů. Běžný postup ve strojovém učení je náhodným inicializací těchto počátečních vektorů. Rozhraní API pro školení Q # akceptuje libovolné pole těchto počátečních vektorů, ale podkladový kód je prozkoumá sekvenčně. Na vícejádrových počítačích nebo ve skutečnosti na jakékoli architektuře paralelního zpracování je vhodné provést několik volání rozhraní API pro školení Q # paralelně s různými inicializacemi parametrů napříč voláními.

#### <a name="how-to-modify-the-hyperparameters"></a>Postup úpravy parametrů

V knihovně QML je nejlepší způsob, jak upravit parametry, přepsáním výchozích hodnot [`TrainingOptions`](xref:microsoft.quantum.machinelearning.trainingoptions)UDT. Chcete-li to provést, zavolejte ho pomocí [`DefaultTrainingOptions`](xref:microsoft.quantum.machinelearning.defaulttrainingoptions) funkce a použijte operátor `w/` k přepsání výchozích hodnot. Pokud například chcete použít měření 100 000 a rychlost učení 0,01:
 ```qsharp
let options = DefaultTrainingOptions()
w/ LearningRate <- 0.01
w/ NMeasurements <- 100000;
 ```
