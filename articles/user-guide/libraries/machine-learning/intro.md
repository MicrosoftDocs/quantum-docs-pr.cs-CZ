---
title: Knihovna pro kvantové strojové učení
description: Přečtěte si, jak se Machine Learning používá v systémech na základě počtu.
author: alexeib2
ms.author: alexeib
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9f7f892fb2b76432942c86163497c22f0c73d51f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833809"
---
# <a name="introduction-to-quantum-machine-learning"></a>Seznámení s Machine Learningmi

## <a name="framework-and-goals"></a>Architektura a cíle

Zátěžové kódování a zpracování informací je neefektivní alternativou pro třídění klasických procesorů strojového učení. Konkrétně umožňuje kódovat data v registrech v obdobích, která jsou stručně relativní vzhledem k počtu funkcí a systematicky se využívaly entanglement jako výpočetní prostředky a využívají měření za běhu pro odvození třídy.
Klasifikátor pro nedodržení okruhu je poměrně jednoduché řešení pro všechna množství, které kombinuje kódování dat s rychle entanglingm nebo disentanglingm okruhem, za nímž následuje měření pro odvození popisků tříd v ukázkách dat.
Cílem je zajistit v případě extrémně velkých prostorů funkcí klasický popis a ukládání okruhů předmětu a také hybridních a klasických školení parametrů okruhu.

## <a name="classifier-architecture"></a>Architektura klasifikátoru

Klasifikace je úloha strojového učení pod dohledem, kde cílem je odvozovat štítky tříd $ \{ y_1, y_2, \ldots, y_d \} $ z určitých ukázek dat. "Školicí data sada" je kolekce vzorků $ \mathcal{D} = \{ (x, y)} $ se známými předem přiřazenými popisky. Tady $x $ je ukázka dat a $y $ je známý popisek s názvem "školení".
Podobně jako u tradičních metod se klasifikace nestandardních hodnot skládá ze tří kroků:
- kódování dat
- Příprava stavu třídění
- měření z důvodu pravděpodobnostní povahy měření se tyto tři kroky musí opakovat několikrát. Jak kódování, tak i výpočet stavu třídění se provádí prostřednictvím *okruhů*v počtu. I když je okruh kódování obvykle řízený daty a bez parametrů, okruh třídění obsahuje dostatečnou sadu podrobnějších parametrů. 

V navrhovaném řešení se okruh třídění skládá z qubit otočení a dvou qubit řízených otočení. Zde popsané parametry jsou úhly otočení. Pro výpočet nenáročných hodnot se ví, že se u zařízení pro rotaci a řízenému otočení označují *univerzální* , což znamená, že jakákoli Jednotková matice je možné rozložit do dostatečně dlouhého okruhu skládajícího se z těchto bran

V navržené verzi se podporuje jenom jeden okruh následovaný jedním odhadem frekvence.
Proto řešení je obdobou nenáročného na počítač, který podporuje Vektorový procesor s nízkou úrovní polynomu.

![Multilayer Perceptron vs. třídění orientované na okruhy](~/media/DLvsQCC.png)

Jednoduchý návrh klasifikátoru pro období se dá porovnat s tradičním řešením SVM (support Vector Machine). Odvození pro ukázku dat $x $ v případě SVM se provádí pomocí optimálního formuláře jádra $ \sum \ alpha_j k (x_j, x) $, kde $k $ je určitá funkce jádra.

Naproti tomu klasifikátorní využití používá prediktivní $p (y │ x, U (\theta)) = 〈 U (\theta) x | M | U (\theta) × 〉 $, která je v duchu podobná, ale technicky poměrně odlišná. Proto když se používá přímočarý kódovací kódování, $p (y │ x, U (\theta)) $ je kvadratická forma ve amplitudách $x $, ale součinitele tohoto formuláře se již nenaučí. místo toho jsou agregovány z prvků matice $U okruhu (\theta) $, což obvykle má výrazně méně možností s možností učení $ \theta $, než je dimenze vektoru $x $. Stupeň polynomu $p (y │ x, U (\theta)) $ v původních funkcích se dá zvýšit na $2 ^ l $ pomocí kódování produktového pole v $l $ kopiích $x $.

Naše architektura zkoumá relativně omezené okruhy, které proto musí být *rychle Entangling* , aby bylo možné zachytit všechny korelace mezi funkcemi dat ve všech oblastech. Příkladem nejužitečnější komponenty pro rychlé Entangling okruhy vidíte na obrázku níže. I když okruh s touto geometrií sestává jenom z $3 n + 1 $ bran, matice s jednotkou váhy, kterou COMPUTE počítá, zajišťuje významné vzájemné rozhovory mezi funkcemi $2 ^ n $.

![Rychle entanglingský okruh na 5 qubits (se dvěma cykly cyklických vrstev).](~/media/5-qubit-qccc.png)

Okruh v předchozím příkladu se skládá z 6 qubit bran $ (G_1, \ldots, G_5; G_ {16} ) $ a 10 2-qubits brány $ (G_6, \ldots, G_ {15} ) $. Za předpokladu, že každá z bran je definovaná s jedním parametrem s příznakem, máme 16 zjistitelné parametry, ale rozměr 5-qubit Hilbert místa je 32. Tato geometrie okruhů se dá snadno zobecnit na jakýkoli $n $-qubit registr, pokud je $n $ lichá, poskytují okruhy s $3 n + 1 $ parametry pro $2 ^ n $ dimenzionální prostor funkcí.

## <a name="classifier-training-as-a-supervised-learning-task"></a>Školení klasifikátoru jako úkol pod dohledem

Školení modelu třídění zahrnuje hledání optimálních hodnot jeho provozních parametrů, aby se maximalizovala Průměrná pravděpodobnost odvození správných školicích popisků v rámci školicích ukázek.
Tady se týkají pouze dodržovali se dvěma klasifikací na úrovni, tj. případ $d = $2 a pouze dvě třídy s popisky $y _1, y_2 $.

> [!NOTE]
> Princip generalizace našich metod pro libovolný počet tříd je nahradit qubits pomocí qudits, tj. jednotky v hodnotě $d $ základních stavů a obousměrnou měření pomocí $d $-Way měření.

### <a name="likelihood-as-the-training-goal"></a>Pravděpodobnost jako cíl školení

Vzhledem k poměrnému okruhu $U (\theta) $, kde $ \theta $ je vektor parametrů a označuje konečné měření pomocí $M $, je průměrná pravděpodobnost správného odvození popisku $ $ \begin{align} \mathcal{L} (\theta) = \frac {1} {| \mathcal{D} |} \left (\ sum_ {(x, y_1) \In\mathcal{D}} P (M = y_1 | U (\theta) x) + \ sum_ {(x, y_2) \in\mathcal{D}} P (M = y_2 | U (\theta) x) \right) \end{align} $ $ WHERE $P (M = y | z) $ je pravděpodobnost měření $y $ v stavovém poli $z $.
V tomto případě stačí pochopit, že pravděpodobnost funkce $ \mathcal{L} (\theta) $ je hladká v $ \theta $ a její deriváty v jakékoli $ \ theta_j $ se dají vypočítat v podstatě stejným protokolem, který se používá pro výpočet pravděpodobnosti samotné funkce. To umožňuje optimalizovat $ \mathcal{L} (\theta) $ podle barevného sklonu proklesání.

### <a name="classifier-bias-and-training-score"></a>Posunutí klasifikátoru a skóre školení

U některých mezilehlých (nebo konečných) hodnot parametrů v $ \theta $ potřebujeme identifikovat jednu skutečnou hodnotu, $b $ ví jako *posun klasifikátoru* k odvození. Pravidlo odvození popisku funguje takto: 
- Vzorový $x $ je přiřazený popisek $y _2 $ if a jenom v případě, že $P (M = y_2 | U (\theta) x) + b > $0,5 (RULE1) (v opačném případě se mu přiřadí jmenovka $y _1 $)

Jasně $b $ musí být v intervalu $ (-0.5, + 0,5) $, aby byly smysluplné.

Školicí případ $ (x, y) \in \mathcal{D} $ se považuje za chybnou *klasifikaci* daného posunutí $b $, pokud je popisek odvozený pro $x $ jako na RULE1 v podstatě jiný než $y $. Celkový počet chybných klasifikací je *školicím skórem* daného třídění, které odpovídá posunu $b $. *Optimální* posun klasifikátoru $b $ minimalizuje skóre školení. Je snadné zjistit, že s ohledem na odhad předpočítaných pravděpodobností $ \{ P (M = y_2 | U (\theta) x) | (x, *) \in\mathcal{D} \} $, optimální posun klasifikátoru lze najít pomocí binárního vyhledávání v intervalu $ (-0,5, + 0,5) $ tím, že se provede maximálně $ \ Log_2 (| \mathcal{D} |). $ kroky.

### <a name="reference"></a>Referenční informace

Tyto informace by měly být dostatečné pro zahájení přehrávání s kódem. Pokud ale chcete získat další informace o tomto modelu, přečtěte si prosím původní návrh: [ *"klasifikátory zaměřené na okruhy", Marie Schuld, Alex Bocharov, Krysta Svore a Nathan* Wiebe](https://arxiv.org/abs/1804.00633)

Kromě ukázky kódu, který se zobrazí v dalších krocích, můžete také začít zkoumat klasifikaci nepočátečních hodnot v [tomto kurzu](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/QuantumClassification) . 
