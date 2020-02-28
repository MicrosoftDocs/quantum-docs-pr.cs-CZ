---
title: Knihovna strojového učení
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.introduction
ms.openlocfilehash: 4c42612fee3a58e15368677bb2c77a70c5680f45
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909785"
---
# <a name="introduction-to-quantum-machine-learning"></a>Seznámení s Machine Learningmi

## <a name="framework-and-goals"></a>Architektura a cíle

Zátěžové kódování a zpracování informací je neefektivní alternativou pro třídění klasických procesorů strojového učení, konkrétně pro kódování dat v registrech v poli doby, které jsou stručně relativní vzhledem k počtu funkcí, systematické využití. entanglement jako výpočetní prostředek a využívejte měření na více jednotek pro odvození třídy.
Klasifikátor pro nedodržení okruhu je poměrně jednoduché řešení pro všechna množství, které kombinuje kódování dat s rychle entanglingm nebo disentanglingm okruhem, za nímž následuje měření pro odvození popisků tříd v ukázkách dat.
Cílem je zajistit v případě extrémně velkých prostorů funkcí klasický popis a ukládání okruhů předmětu a také hybridních a klasických školení parametrů okruhu.

## <a name="classifier-architecture"></a>Architektura klasifikátoru

Klasifikace je úloha strojového učení pod dohledem, kde cílem je odvozovat štítky třídy $\{y_1, y_2, \ldots, y_d\}$ z určitých ukázek dat. "Školicí data sada" je kolekce vzorků $ \mathcal{D} =\{(x, y)} $ se známými předem přiřazenými popisky. Tady $x $ je ukázka dat a $y $ je známý popisek s názvem "školení".
Podobně jako u tradičních metod se klasifikace nestandardních hodnot skládá ze tří kroků:
- kódování dat
- Příprava stavu třídění
- měření z důvodu pravděpodobnostní povahy měření se tyto tři kroky musí opakovat několikrát. Měření se může zobrazit jako nelineární aktivace, která odpovídá nelineární aktivaci.
Jak kódování, tak i výpočet stavu třídění se provádí prostřednictvím *okruhů*v počtu. I když je okruh kódování obvykle řízený daty a bez parametrů, okruh třídění obsahuje dostatečnou sadu podrobnějších parametrů. 

V navrhovaném řešení se okruh třídění skládá z qubit otočení a dvou qubit řízených otočení. Zde popsané parametry jsou úhly otočení. Pro výpočet nenáročných hodnot se ví, že se u zařízení pro rotaci a řízenému otočení označují *univerzální* , což znamená, že jakákoli Jednotková matice je možné rozložit do dostatečně dlouhého okruhu skládajícího se z těchto bran

![Multilayer Perceptron vs. třídění orientované na okruhy](~/media/DLvsQCC.png)

Tento model můžeme porovnat s Multilayer Perceptron a získat tak lepší porozumění základní struktuře. V Perceptron prediktivní $p (y | x, \theta) $ je parametr podle sady závaží $ \theta $, která určuje lineární funkce připojující nelineární funkce aktivace (neurons). Tyto parametry mohou být vyškolené pro vytvoření modelu. Ve výstupní vrstvě můžeme získat pravděpodobnost vzorku patřícího ke třídě pomocí nelineárních funkcí aktivace, jako je softmax. V klasifikátoru zaměřeném na okruhy se předpokládá, že se v rozstředcích rozqubit a ve dvou qubit řízených otočeních modelu přesměrují úhly otočení. Podobným způsobem mohou být tyto parametry vyškoleny pomocí hybridního počtu chyb/klasických verzí algoritmu gradientu. Chcete-li vypočítat výstup namísto použití nelineárních funkcí aktivace, je pravděpodobnost třídy získána čtením opakovaných měření v konkrétní qubit po řízených otočeních. Pro kódování klasických dat ve státě, který používá ovladatelného okruhu kódování pro přípravu stavu.

Naše architektura zkoumá relativně omezené okruhy, které proto musí být *rychle Entangling* , aby bylo možné zachytit všechny korelace mezi funkcemi dat ve všech oblastech. Příkladem nejužitečnější komponenty pro rychlé Entangling okruhy vidíte na obrázku níže. I když okruh s touto geometrií sestává jenom z $3 n + 1 $ bran, matice s jednotkou váhy, kterou COMPUTE počítá, zajišťuje významné vzájemné rozhovory mezi funkcemi $2 ^ n $.

![Rychle entanglingský okruh na 5 qubits (se dvěma cykly cyklických vrstev).](~/media/5-qubit-qccc.png)

Okruh v předchozím příkladu se skládá z 6 qubit bran $ (G_1, \ldots, G_5; G_{16}) $ a 10 2-brány qubits $ (G_6, \ldots, G_{15}) $. Za předpokladu, že každá z bran je definovaná s jedním parametrem s příznakem, máme 16 zjistitelné parametry, ale rozměr 5-qubit Hilbert místa je 32. Tato geometrie okruhů se dá snadno zobecnit na jakýkoli $n $-qubit registr, pokud je $n $ lichá, poskytují okruhy s $3 n + 1 $ parametry pro $2 ^ n $ dimenzionální prostor funkcí.

## <a name="classifier-training-as-a-supervised-learning-task"></a>Školení klasifikátoru jako úkol pod dohledem

Školení modelu třídění zahrnuje hledání optimálních hodnot jeho provozních parametrů, aby se maximalizovala Průměrná pravděpodobnost odvození správných školicích popisků v rámci školicích ukázek.
Tady se týkají pouze dodržovali se dvěma klasifikací na úrovni, tj. případ $d = $2 a pouze dvě třídy s popisky $y _1, y_2 $.

> [!NOTE]
> Princip generalizace našich metod pro libovolný počet tříd je nahradit qubits pomocí qudits, tj. jednotky v hodnotě $d $ základních stavů a obousměrnou měření pomocí $d $-Way měření.

### <a name="likelihood-as-the-training-goal"></a>Pravděpodobnost jako cíl školení

Vzhledem k poměrnému okruhu $U (\theta) $, kde $ \theta $ je vektor parametrů a označuje konečné měření pomocí $M $, je průměrná pravděpodobnost správného odvození popisku $ $ \begin{align} \mathcal{L} (\theta) = \frac{1}{| \mathcal{D} |} \left (\ sum_ {(x, y_1) \in\mathcal{D}} P (M = y_1 | U (\theta) x) + \ sum_ {(x, y_2) \in\mathcal{D}} P (M = y_2 | U (\theta) x) \right) \end{align} $ $ WHERE $P (M = y | z) $ je pravděpodobnost měření $y $ v stavovém poli $z $.
V tomto případě stačí pochopit, že pravděpodobnost funkce $ \mathcal{L} (\theta) $ je hladká v $ \theta $ a její deriváty v jakékoli $ \ theta_j $ se dají vypočítat v podstatě stejným protokolem, který se používá pro výpočet pravděpodobnosti samotné funkce. To umožňuje optimalizovat $ \mathcal{L} (\theta) $ podle barevného sklonu proklesání.

### <a name="classifier-bias-and-training-score"></a>Posunutí klasifikátoru a skóre školení

U některých mezilehlých (nebo konečných) hodnot parametrů v $ \theta $ potřebujeme identifikovat jednu skutečnou hodnotu, $b $ ví jako *posun klasifikátoru* k odvození. Pravidlo odvození popisku funguje takto: 
- Vzorový $x $ je přiřazený popisek $y _2 $ if a jenom v případě, že $P (M = y_2 | U (\theta) x) + b > $0,5 (RULE1) (v opačném případě se mu přiřadí jmenovka $y _1 $)

Jasně $b $ musí být v intervalu $ (-0.5, + 0,5) $, aby byly smysluplné.

Školicí případ $ (x, y) \in \mathcal{D} $ se považuje za chybnou *klasifikaci* daného posunutí $b $, pokud je popisek odvozený pro $x $ jako na RULE1 v podstatě jiný než $y $. Celkový počet chybných klasifikací je *školicím skórem* daného třídění, které odpovídá posunu $b $. *Optimální* posun klasifikátoru $b $ minimalizuje skóre školení. Je snadno vidět, že s ohledem na odhad předpočítaných pravděpodobností $\{ P (M = y_2 | U (\theta) x) | (x, *) \in\mathcal{D} \}$, optimální posun klasifikátoru můžete najít pomocí binárního vyhledávání v intervalu $ (-0,5, + 0.5) $ tak, že se nastaví maximálně $ \ log_2 (| \mathcal{D} |). $ kroky.

### <a name="reference"></a>Referenční informace

Tyto informace by měly být dostatečné pro zahájení přehrávání s kódem. Pokud ale chcete získat další informace o tomto modelu, přečtěte si prosím původní návrh: [ *"klasifikátory zaměřené na okruhy", Marie Schuld, Alex Bocharov, Krysta Svore a Nathan* Wiebe](https://arxiv.org/abs/1804.00633)
